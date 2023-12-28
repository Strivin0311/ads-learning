# 1602.00763 SORT 

SORT——Simple Online and Realtime Tracking

这篇论文里面讨论了简单的帧与帧的跟踪，使用的是恒定速率模型。

- **关键步骤**：卡尔曼滤波预测Track=>将预测后的Track与当前帧中的Detection使用匈牙利算法进行匹配（IOU）=>卡尔曼滤波更新。

该方法主要拆分为两个部分：**Detection** 和 **卡尔曼滤波**的Predict和Update（对于Track）。

> 借用下知乎大佬Harlek的绘制的图片，侵删

![](.\Picture\SORT & DeepSORT\SORT.webp)

> Tracks: 是指在已经匹配成功的所有目标状态量（**估计值**），正是通过Tracks才能进行卡尔曼滤波的预测。
>
> Detections: 是通过目标检测器获取的当前帧的检测框（**观测值**）

**卡尔曼滤波**实质上是一种对数据的加权，可以预测下次Track并根据实际观测结果进行更新。

> **卡尔曼滤波**分为两个过程：**预测**和**更新**。预测过程：当一个小车经过移动后，且其初始定位和移动过程都是高斯分布时，则最终估计位置分布会更分散，即更不准确；更新过程：当一个小车经过传感器观测定位，且其初始定位和观测都是高斯分布时，则观测后的位置分布会更集中，即更准确。

> IOU match:  intersection-over-union (IOU) ，交并比，即两个bounding box的交集和并集取比。计算Predict和Detection的bounding box的IOU距离得到一个**代价矩阵**，使用匈牙利算法（**Hungarian algorithm**）进行二分图匹配，时间复杂度为$O(n^3)$。

能够互相匹配的Track和Detection，进行卡尔曼滤波更新即可；对于没有匹配成功的Detection，则需要先创建对应的New Track；若有没有匹配成功的Track，论文中设置了一个时间间隔T_lost来对这些Track进行保护，但是因为速率模型和论文范围限制，T_lost被设置为1，表现为Track匹配失败即被删除。

# 1702.07402 DEEPSORT 

DEEPSORT——the improment of SORT

由于现实中目标运动多变且遮挡频繁，SORT算法的身份转换次数较多。

DeepSORT是对SORT算法的改进，主要区别在于匹配时增添了级联匹配（Matching Cascade）和对Tracks进行了确认。

- **关键步骤**：卡尔曼滤波预测Track=>将预测后的Track与当前帧中的Detection使用匈牙利算法进行匹配（**级联匹配**和IOU匹配）=>卡尔曼滤波更新。

![](.\Picture\SORT & DeepSORT\DeepSORT.webp)

- **级联匹配**（Matching Cascade）：

![](\Picture\SORT & DeepSORT\Matching Cascade.webp)

级联匹配是DeepSORT不同于SORT的最重要区别，使用了马氏距离和余弦距离两种度量。

> 马氏距离（Mahalanobis Distance）是由印度统计学家马哈拉诺比斯(P. C. Mahalanobis)提出的，表示数据的协方差距离。它是一种有效的计算两个未知样本集的相似度的方法。与欧氏距离不同的是它考虑到各种特性之间的联系并且是尺度无关的，即独立于测量尺度。对于一个均值为μ，协方差矩阵为$\Sigma$的多变量向量，其n维空间中的马氏距离为：$d(x, y)=\sqrt{(x-y)^T\Sigma^{-1}(x-y))}$

> 余弦距离(Cosine Distance)也可以叫余弦相似度。 几何中夹角余弦可用来衡量两个向量方向的差异，机器学习中借用这一概念来衡量样本向量之间的差异。相比距离度量，余弦相似度更加注重两个向量在方向上的差异，而非距离或长度上。n维空间中的余弦距离为：$$\cos(x, y)=\frac{x\cdot y}{|x|\cdot|y|}=\frac{\sum_{i=1}^nx_iy_i}{\sqrt{\sum_{i=1}^nx_i^2}\sqrt{\sum_{i=1}^ny_i^2}}$$

**“这两个度量标准通过服务于分配问题的不同方面来相互补充。一方面，马氏距离提供了基于运动的物体可能位置的信息，这对短期预测特别有用。另一方面，余弦距离考虑了外观信息（Re-ID特征），这些信息对于恢复长期遮挡后的身份特别有用，此时运动的区别性较弱。为了构建关联问题，我们使用加权和将两个指标组合起来。”**

因此成本函数表示为：$c_{i,j}=λ*d^{(1)}(i,j)+(1−λ)*d^{(2)}(i,j)$

> 在本论文中，作者发现当存在大量相机运动时，设置λ = 0 是一个合理的选择。在这种设置中，关联成本项中只使用了外观信息。但是马氏距离仍通过阈值矩阵（Gate Matrix）对代价矩阵（Cost Matrix）做了一次**阈值限制**。

根据此成本函数即可生成cost_matrix，运用匈牙利算法。

此处**匈牙利算法**运行过程根据track的missing_age从小到大进行循环匹配，这也是级联匹配叫法的来源。

> DeepSORT相对于SORT，对Track增加了missing_age变量，表示已经有missing_age帧没有与Detection成功匹配，是一种对Track的保存和保护。

- **Track的确认（confirm）**

 对于没有匹配到Track的Detection，与SORT不同的是，DeepSORT将为其新创建的New Track标记为unconfirmed。
该变量的设立主要是为了防止数据集的一些误判，来使得产生一个轨迹的条件更加严格。

在实验部分中，论文指出DEEPSORT相较于SORT身份转换次数减少了45%。

目前正在研究下面这个相关项目的代码：[GitHub - ZQPei/deep_sort_pytorch: MOT using deepsort and yolov3 with pytorch](https://github.com/ZQPei/deep_sort_pytorch)

> 2023.9.8 211220031 张佳瑞 第一次更新至此
