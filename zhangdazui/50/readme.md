# 50 | 推荐系统（下）：如何通过SVD分析用户和物品的矩阵？

## SVD 回顾

SVD 的主要概念和步骤。如果矩阵 X 是对称的方阵，那么我们可以求得这个矩阵的特征值和特征向量，并把矩阵 X 分解为特征值和特征向量的乘积。

假设我们求出了矩阵 X 的 n 个特征值 λ_1，λ_2，…，λ_n，以及这 n 个特征值所对应的特征向量 v_1，v_2，…，v_n，那么矩阵 X 可以表示为：

X=VΣV^{-1}

其中，V 是这 n 个特征向量所张成的 n×n 维矩阵，而 Σ 是这 n 个特征值为主对角线的 n×n 维矩阵。这个过程就是特征分解

可以把 X 的转置 X’ 和 X 做矩阵乘法，得到一个 n×n 维的对称方阵 X’X，并对这个对称方阵进行特征分解。

分解的时候，我们得到了矩阵 X’X 的 n 个特征值和对应的 n 个特征向量 v，其中所有的特征向量叫作 X 的右奇异向量。

第一种方式是计算下面这个式子：

σ_i=\frac{X_{v_{i}}}{u_{i}}

其中 v_i 和 u_i 都是列向量。一旦我们求出了每个奇异值 σ，那么就能得到奇异值矩阵 Σ。

第二种方式是通过 X’X 矩阵或者 XX’ 矩阵的特征值之平方根，来求奇异值。

