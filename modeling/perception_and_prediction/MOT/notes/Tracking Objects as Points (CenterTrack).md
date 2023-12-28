# 2004.01177 Tracking Objects as Points（CenterTrack）

上次我读的文章介绍了一种将目标检测和特征提取直接放在一个网络里输出来加速MOT系统的JDE算法，注意到，JDE仍然是anchor-base类型的算法，同时它仍然是双阶段的。这篇论文基于CenterNet网络，实现了一个anchor-free的算法，是真正意义上的端到端算法。

之前的TBD（检测后追踪）模式，将检测和追踪分为两步。首先在每帧中找到所有目标，然后追踪的任务就变成了一个边界框关联。因为给定了检测的结果，只需要关注如何将相同的目标连接起来（轨迹）即可。但是大多数的关联策略都是复杂的，高计算量的。主要有两个缺点：1.数据关联的时候直接放弃了图片的外貌特征或者需要极大的计算力来进行特征提取；2.检测与追踪分离。

为了降低计算量，本文的模型以基于点的追踪将目标检测和追踪同时进行。本模型直接和检测联合进行学习，几乎不需要关联。在使用过去帧进行学习的同时，可以利用他的线索来对消失的或者遮挡的目标进行恢复。

在了解CenterTrack之前，我们需要简单了解一下CenterNet这个网络。CenterNet提出于论文1904.07850: Objects as Points 中，也是本篇论文的几位主要作者的研究成果。

## CenterNet

CenterNet网络的结构相对而言简单，主要包括backbone**提取图片特征**，然后是**反卷积模块Deconv**对特征图进行上采样，最后三个分支卷积网络分别用来预测heatmap、目标的宽高和目标的中心点坐标。值得注意的是反卷积模块，其包括三个反卷积组，**每个组都包括一个3*3的卷积和一个反卷积**。

CenterNet使用的backbone，论文中提出可以使用三种网络：Resnet、DLA和Hourglass，这里使用的是Hourglass，用了两个Hourglass通过joint连接在一起。

CenterNet的输出包括三层：

- **HeatMap**，大小为（W/4,H/4,80），输出不同类别物体中心点的位置

  > ![CenterTrack_2](.\Picture\CenterTrack\CenterTrack_2.png)
  >
  > 这里用的是基于高斯核的热图，公式中的x, y为步长块的位置，px, py为关键点位置。可以看出，当枚举块的位置和GT关键点坐标接近重合的时候，高斯核输出值接近为1；当枚举块位置和GT关键点相差很大时，高斯核输出值接近为0。
  >
  > 因此这样我们就得到了诸如下面这样的一个热点图，就可以通过maxpooling进行Decode得到目标的中心点位置。
  >
  > ![CenterTrack_3](.\Picture\CenterTrack\CenterTrack_3.png)

- **Offset**，大小为（W/4,H/4,2），对HeatMap的输出进行精炼，提高定位准确度

- **Height&Width**,大小为（W/4,H/4,2），预测以关键点为中心的检测框的宽高

CenterNet有哪些优势：

- 我们分配的锚点仅仅是放在位置上，没有尺寸框。没有手动设置的阈值做前后景分类。

  ​	（像Faster RCNN会将与GT IOU >0.7的作为前景，<0.3的作为背景，其他不管）；

- 每个目标仅仅有一个正的anchor，它仅仅取自我们提取关键点特征图上局部峰值点（local peaks），所以它不需要考虑是否是positive anchor亦或是区分anchor是否是背景或者前景，故此它不需要使用NMS；

- CenterNet 的输出分辨率的下采样因子是4，相比较传统目标检测而言（通常为16），使用了更大分辨率的输出特征图。

其他具体细节诸如Decode、loss等请见论文https://doi.org/10.48550/arXiv.1904.07850

## CenterTrack

那么在CenterNet基础上，作者在本篇论文中提出了CenterTrack。

下面让我们关注一下CenterTrack的网络结构。

![CenterTrack_4](.\Picture\CenterTrack\CenterTrack_4.png)

- 首先，与CenterNet只有一张RGB图片的输入不同的是，CenterTrack的输入为**当前帧和前一帧的两张RGB图片（大小为（W,H,3））**与**一张前一帧的Heatmap（大小为（W,H,1））**，所以如论文中所说，CenterTrack相比CenterNet多了4个输入通道，即为RGB（3通道）+ Heatmap（1通道）。

  > CenterTrack **localizes objects** and **predicts their associations with the previous frame.** The architecture of CenterTrack is essentially **identical to CenterNet**, with **four additional input channels.**

  接着，需要对这三个输入进行信息融合，这里论文采取的方法非常的简单：即将这三个输入**各自依次通过简单卷积层、批归一化层和激活函数**，最后再**直接按位相加即得到了特征图**。

- 然后将这个特征图**输入一个特征网络**中，这个网络可以是Resnet、可以是DLA等。比如说Resnet，就先进行32倍下采样，得到特征图宽高（W/32,H/32），再进行3次上采样，最终得到一个宽高为（W/4,H/4）的特征图。**不论选择什么网络，最终输出的特征图的宽高都应该是（W/4,H/4）。**

- 因为需要预测追踪目标，输出上CenterTrack相比CenterNet增加一个输出，每个输出都是从上面获得的特征图通过各自的Head模块得到的。

  每个head的定义也比较简单，仅由两个卷积层中间夹着一个ReLU激活函数组成。

  具体的各个输出特征图如下所示：

  > 源码中四层输出分别为：['hm', 'reg'(=offset), 'wh', 'tracking']。在centerNet中，作者提到直接使用heatmap中峰值的预测值作为该点预测的置信度

  - （1）**HeatMap**，大小为（W/4,H/4,80）,检测框中心点**位置分布热力图**
  - （2）**Offset**，大小为（W/4,H/4,1），对HeatMap的输出进行精炼，提高定位准确度
  - （3）**Height&Width**,大小为（W/4,H/4,1），点对应的检测框的**宽高**
  - （4）**Displacement prediction**, 大小为（W/4,H/4,2），检测框中心点在前后帧的**位移**

  前三条输出就对应CenterNet中的输出，与CenterNet那篇论文中的内容基本一致。论文主要对新加的第四条输出进行了讨论，我们关注的重心也在这一部分。

  第四条为Displacement prediction，表示检测框的中心点在前后帧的位移。而**物体i的中心点的位移**为**时刻t-1中心点的位置$p_i^{t-1}$** 与**时刻t中心点的位置$p_i^{t}$** 的**变化**，表达式为$p_i^{t}-p_i^{t-1}$，即为真实值。

  故此通过displacement prediction特征图${\hat D}$与上述真实值即可得到该部分的损失函数：

  ![CenterTrack_5](.\Picture\CenterTrack\CenterTrack_5.png)

  当这个位移损失足够低，使用一个**贪心匹配算法**来完成在时序上连接目标。在${\hat p}$上每个检测目标，将过去帧中未匹配的点且距离在${\hat p-\hat D}$内按置信度${\hat w}$ 递减排序，若在半径K内未匹配上，则生成一条新路径。K定义为每个预测轨迹的预测边界框的高和宽的几何均值。

## 实验部分

实验基于CenterNet，使用DLA作为网络backbone，优化器使用学习率为1,25e-4的Adam，batchsize为32。数据增强使用随机水平翻转，随机大小裁剪和颜色抖动。每个实验训练70个epoch，学习率在60个epoch下降10倍。各个数据集结果如下：

![CenterTrack_6](.\Picture\CenterTrack\CenterTrack_7.png)

![CenterTrack_7](.\Picture\CenterTrack\CenterTrack_7.png)

消融学习：

![Centertrack_8](.\Picture\CenterTrack\Centertrack_8.png)

![CenterTrack_9](.\Picture\CenterTrack\CenterTrack_9.png)

与其他运动模型的比较：

![CenterTrack_10](.\Picture\CenterTrack\CenterTrack_10.png)

## 总结

本文提出了一个端到端实时的目标检测和跟踪框架。方法以两个帧和一个先验的热图作为输入，对当前帧产生检测和跟踪偏移量。跟踪器完全是本地的，并通过时间贪心地关联对象，能够实时运行并且是Online模式。

但是CenterTrack的问题在于**只关联连续两帧之间的检测框**，那么就很难形成长期的关联和依赖，这样其实非常容易产生ID切换等情况的发生。但是作者在论文中指出，虽然如此，但是CenterTrack能够做到速度和精度trade-off，并且通过实验发现，该办法的精度还是不错的。

作者在论文中附上了CenterTrack的实现代码，在此附出：https://github.com/xingyizhou/CenterTrack

> 2023.12.22 211220031 张佳瑞 第四次更新至此