# 43 | PCA主成分分析（下）：为什么要计算协方差矩阵的特征值和特征向量

PCA 主成分分析。这个方法主要是利用不同维度特征之间的协方差，构造一个协方差矩阵，然后获取这个矩阵的特征值和特征向量。根据特征值的大小，我们可以选取那些更为重要的特征向量，或者说主成分。最终，根据这些主成分，我们就可以对原始的数据矩阵进行降维。

## PCA 背后的核心思想

为什么我们要使用样本数据中，各个维度之间的协方差，来构建一个新的协方差矩阵？要弄清楚这一点，首先要回到 PCA 最终的目标：降维。降维就是要去除那些表达信息量少，或者冗余的维度。

### 为什么要使用协方差矩阵？

1. 认为样本在某个特征上的差异就越大，那么这个特征包含的信息量就越大，就越重要。相反，信息量就越小，需要被过滤掉。很自然，我们就能想到使用某维特征的方差来定义样本在这个特征维度上的差异。

2. 我们要看如何发现冗余的信息。如果两种特征是有很高的相关性，那我们可以从一个维度的值推算出另一个维度的值，所表达的信息就是重复的。

考虑到协方差既可以衡量信息量的大小，也可以衡量不同维度之间的相关性，因此我们就使用各个维度之间的协方差所构成的矩阵，作为 PCA 分析的对象。

### 为什么要计算协方差矩阵的特征值和特征向量？

第一个角度是对角矩阵。所谓对角矩阵，就是说只有矩阵主对角线之上的元素有非 0 值，而其他元素的值都为 0。我们刚刚解释了协方差矩阵的主对角线上，都是表示信息量的方差，而其他元素都是表示相关性的协方差。既然我们希望尽可能保留大信息量的维度，而去除相关的维度，那么就意味着我们希望对协方差进行对角化，尽可能地使得矩阵只有主对角线上有非 0 元素。

第二个角度是特征值和特征向量的几何意义。在向量空间中，对某个向量左乘一个矩阵，实际上是对这个向量进行了一次变换。在这个变换的过程中，被左乘的向量主要发生旋转和伸缩这两种变化。
