# 29 | 归一化和标准化：各种特征如何综合才是最合理的？

**特征工程**：包括特征选择、特征数值转换

**特征数值转换**：使用统计中的数据分布，对连续型的数值特征进行转换，让多个特征的结合更有效。

## 为什么需要特征变换？

不同特征之间没有可比性。

**因变量连续回归分析**：采用的是研究一个或多个随机变量 y1​，y2​，…，yi​ 与另一些变量 x1​，x2​，…，xk​ 之间关系的统计方法，又称多重回归分析。

如果因变量和自变量为线性关系时，就称为**线性回归模型**；
如果因变量和自变量为非线性关系，则称为**非线性回归分析模型**。

## 两种常见特征转换方法

### 归一化

定义：其实就是获取原始数据的最大值和最小值，然后把原始值线性变换到[0,1]之间。

“归一化”这个词在不同的领域的含义可能不同。这里我们特指基于最大和最小值的变换。

### 标准化

定义：是基于正态分布的 z 分数（z-score）标准化（Standardization）。该方法假设数据呈现标准正态分布。

正态分布是连续随机变量概率分布的一种。在现实生活中，大量随机现象的数据分布都近似于正态分布。

标准正态分布是正态分布的一种，平均数为 0，标准差为 1。