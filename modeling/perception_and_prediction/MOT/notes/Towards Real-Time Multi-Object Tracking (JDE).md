# 1909.12605 JDE

这段时间我看了一篇MOT领域比较经典的论文 Towards Real-Time Multi-Object Tracking。这篇论文由清华大学于2019年发表，其创新性地将**目标检测环节和外观特征信息提取环节两部分融合设计**为一个网络，从而极大地提升了多目标跟踪算法的推理速度，达到了接近**实时的帧数(near real-time)**。其存在的不足在于还没有能够完全解决Detection和REID两任务之间的矛盾，仅仅将detection和embedding结合起来，实际上并未作出显著的创新。

# 1. Abstract

本论文之前的多目标跟踪(MOT)算法主要遵从“检测后跟踪”的范式。顾名思义，其包含两个阶段：
1）检测模型获得目标的位置信息。
2）外观特征向量提取模型获得向量并用于数据关联。
分别执行这两个阶段会导致严重的效率问题，整个运行时间基本等于两阶段分别执行时间之和。

该论文提出了一种将“Detection”与“Embedding提取”任务依赖一个共享模型学习的MOT网络设计方式：
1）将特征向量(embedding)提取网络放入单阶段目标检测模型中，从而能够通过一个网络输出这两个任务所需的结果。
2）提出了一种新的，简单且快速的数据关联方法，适用于上述联合网络。

最终经过实验验证，提出的MOT算法速度大幅提升、精度和分离式(SDE)的MOT算法中的SOTA基本持平。

# 2. Introduction

论文中提到，MOT范式主要有三种：

1. SDE模式：即分离式，先通过Detection网络获取BBox，再将BBox输入ReID网络中进行特征提取。
2. Two-stage模式：先通过Region Proposal Network找出目标对应特征图，再将特征图输入ReID网络中进行特征提取。

上述两种模式都是将detection step 和 association step 分成两阶段，区别在于输入ReID网络的是图像还是特征图。

3. JDE模式：即论文中提出的 Joint Learning of Detection and Embedding(JDE) 联合式，将检测任务和REID任务融合到一个网络中。

![](.\Picture\JDE\3methods.png)

# 3. Joint Learning of Detection and Embedding

## 3.1 Promblem Settings

要建立这样一个 Joint learing 模型，需要有以下两个目标：

第一个目标要求模型能够准确探测目标。

第二个目标要求外观嵌入具有以下特性：同ID的的目标相似度高、不同ID的目标相似度低。相似度可以是欧氏距离或余弦距离。

论文中提到，从技术上讲，如果两个目标都得到满足，即使是简单的关联策略，如匈牙利算法，也能产生比较好的跟踪结果。

## 3.2 Architecture Overview

![](.\Picture\JDE\ArchitectureOverview.png)

特征提取网络采用Darknet53，后面接特征金字塔结构FPN，输出结果为分别对原图下采样1/8, 1/16, 1/32倍。输出维度为$(6A+D)∗H∗W$，其中，$A$表示预设的anchor数，$D$表示外观特征向量的维数。其output主要由三部分构成：
1) the box classication results of size $2A\times H\times W$;
2) the box regression coefficients of size $4A\times H\times W$;
3) the dense embedding map of size $D\times H\times W$.

> > We employ DarkNet-53 [27] as the backbone network in JDE.
>
> 这里提到的DarkNet-53来自论文1804.02767: Yolov3: An incremental improvement. 即JDE使用的核心网络是Yolov3网络
>

## 3.3 Learning to Detect

这一部分解决第一个目标，即要求模型能够准确探测目标。

总的来说，Detection与标准 RPN 类似，但有论文中作了两处修改。

一是设置anchor。

anchors数目设置为12个，即每个通道分配3个anchor，anchor的ratio设置为常用值1：3，尺寸根据training dataset重新聚类。

二是正负例判定。

IOU > 0.5, 则判定为**前景**。
IOU < 0.4, 则判定为**背景**。

选择这个阈值的原因是**减少误报**。

> 我们的初步实验表明，这些阈值能有效抑制误报，而误报通常发生在严重遮挡的情况下。

**检测环节的损失函数**主要由两部分构成，**前景/背景分类**(foreground/background classification) 和 **位置回归**(bounding box regression)。
1）前景/背景分类：$\mathcal L_\alpha$，Cross-Entrophy Loss 交叉熵损失
2）目标位置回归： $\mathcal L_\beta$ ，Smooth-L1 Loss

## 3.4 Learning Appearance Embeddings

这一部分解决第二个目标，即要求外观嵌入有同ID的的目标相似度高、不同ID的目标相似度低的特性。

作者首先提出了经典的Triplet loss算法来作为损失函数：

![](.\Picture\JDE\Triplet.png)

其中 $f^T$ 是mini-batch中被选作anchor的实例，$f^+$ 代表与$f^T$ 相关的**正样本**，$f^-$ 代表负样本。

但是Triplet loss仍有许多局限。首先是训练集的采样空间巨大。其次，使用Triplet loss进行训练可能不稳定，收敛速度可能很慢。

为此，作者提出了a smooth upper bound of the triplet loss：

![](.\Picture\JDE\Triplet_smooth_upper_bound_1.png)

也即：

![](.\Picture\JDE\Triplet_smooth_upper_bound_2.png)

可以发现，$\mathcal L_{upper}$的第二种表达非常类似交叉熵的损失的公式：

![](.\Picture\JDE\Cross_Entropy.png)

其中，我们用 $g^+$ 表示**正类**（anchor实例所属）的**权重**，用 $g^-$ 表示**负类**的**权重**。

而$\mathcal L_{upper}$和$\mathcal L_{CE}$有以下两点不同：

- 首先，交叉熵损失采用可学习的**类权重作为类实例的代理**，而不是直接使用实例的嵌入。
- 其次，所有**负类**都参与到$\mathcal L_{CE}$的损失计算中，这样anchor实例就会从嵌入空间中的**所有负类**中抽离出来。相比之下，在$\mathcal L_{upper}$中，anchor实例只从**采样的负实例**中抽离。

所以，在作者的估计中，表现应是$\mathcal L_{CE} > \mathcal L_{upper} > \mathcal L_{triplet}$，实验也证实了这一点，故最终选择的损失函数是Cross Entropy，记作$\mathcal L_{\gamma}$。

## 3.5 Automatic Loss Balancing

根据上述各个部分的设计可知，该网络存在3个不同尺度的输出通道、且每个通道输出包括3个任务的信息（foreground/background, bbox regression, appearance embedding）。因此，目前存在一个多任务、多尺度之间相互平衡的问题。按照基本的加权思想可以表示为：

![](.\Picture\JDE\total.png)

其中，M为多尺度通道数（number of prediction heads），即为3；$\alpha, \beta, \gamma$是损失权重。

朴素的做法是就是调参，但是想要得到比较好的结果相对困难。

因此作者提供了一个自动学习的策略：

![](.\Picture\JDE\Automatic_learning_scheme.png)

其中$s^i_j$ 是一个可学习的参数，表示不同损失函数的权重。

## 3.6 Online Association

论文中提到过，网络能够较好地完成两个主要目标后，只需通过简单的Association算法就可以得到好的效果，但是作者还是提供了一个关联机制：

> 1. 初始化一个轨迹池(tracklet pool)，一个轨迹(tracklet)由其外观向量$e_i$和运动状态$m_i$决定
>
> 2. 对新的一帧，计算这一帧的各个目标和轨迹池中各条轨迹的两两之间的成本矩阵，包括
>    1）动态成本矩阵$A_m$ (motion affinity matrix)：马氏距离计算
>    2）外形特征成本矩阵$A_e$ (appearance affinity matrix)：余弦距离计算
>    将两部分成本矩阵加权相加：
>    $$
>    C = \lambda A_e+(1-\lambda)A_m
>    $$
>    计算得到最终的成本矩阵，使用匈牙利算法进行匹配，将该帧的目标关联到轨迹池中的轨迹上去。
>
> 3. 根据第二步，匹配上的轨迹需要更新其外观向量$e_i$和运动状态$m_i$
>
>    1）$m_i$ 通过卡尔曼滤波更新
>    2）$e_i$通过滑动平均方法更新：$e_i^t=\alpha e_i^{t−1}+(1−\alpha)f_i^t$
>
>    其中$\alpha=0.9$，$f_i^t$表示该帧目标的外观特征向量。
>
> 4. 如果一个新目标出现超过2帧，则新建一条轨迹到轨迹池。
> 5. 如果一个轨迹超过30帧没更新，则终止这条轨迹

相比与SORT的级联匹配，本文中提出的方法更加简单，因为它只对每一帧应用一次关联，并且它利用了缓冲池来处理那些很快丢失的小轨迹。

> 作者甚至还实现了 high FPS 的 Kalman Filter

最后，作者还将自己的association方法与SORT进行了对比，结果上确实有一定的提升。

# 4 Experiments

## 4.1 Compared with SDE

![Compared_with_SDE](.\Picture\JDE\Compared_with_SDE.png)

作者据此提出了三条结论：

1）JDE的速度明显快于其他MOT算法，且精度也基本能够和其他SDE算法持平
2）JDE不需要额外的REID模型获得embeding，也能获得足够好的精度表现
3）JDE在目标密度(density)增大很多的情况下，其推理速度基本不会收到影响，这明显优于其他所有SDE模式的网络组合

## 4.2 Compared with SOTA

![Compared_with_SOTA](.\Picture\JDE\Compared_with_SOTA.png)

通过分析，作者得出以下结论：

1. 速度上，JDE至少优于其他算法2到3倍。
2. 精度上，相较于POI还是有一定的差距。
3. 与现有方法相比，JDE 的 IDF1 分数较低且IDswitch较多。起初，作者怀疑其原因是共同学习的嵌入可能比单独学习的嵌入弱。然而，当作者用单独学习的嵌入式替换联合学习的嵌入式时，IDF1 分数和 ID 切换次数几乎没有变化。最后作者发现，主要原因在于当多个行人有大量重叠时，检测不准确。这种不准确的方框会带来大量的 ID 切换，不幸的是，这种 ID 切换经常发生在轨迹的中间，因此 IDF1 分数较低。如何改进 JDE，以便在行人有明显重叠时预测出更准确的方框，仍是一个有待解决的问题。

# 5. Conclusion

该论文提出了新的MOT方法JDE，它是一个可以在共享模型中学习目标检测和外观特征的算法，极大地减少了推理时间，能够接近实时性效果，但是精度却不是很好。此外，论文还提出了一种新的关联方法。

这篇文章提出的JDE确实在当时提高了MOT的速度，但其实它只是将detection和embedding的过程放在了一个网络中同时处理而已，实际上JDE仍然是双阶段的：1) 检测 + embedding  2)数据关联， 而且也并不是anchor-free的。目前我正在看centerTrack那篇论文Tracking Objects as Points，它较好地解决了这个问题。



通过访问论文中提供的github网站，我拿到了原项目的代码，但是由于Python更新到Python3，许多库的支持情况发生了变化，我无法正常运行。好在作者在仓库里推荐了samylee复现的C++代码，因此得以运行，在此致谢，samylee复现的代码仓库于下：

[samylee/Towards-Realtime-MOT-Cpp: A C++ codebase implementation of Towards-Realtime-MOT (github.com)](https://github.com/samylee/Towards-Realtime-MOT-Cpp)

> 2023.11.18 211220031 张佳瑞 第三次更新至此