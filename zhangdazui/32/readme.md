# 32 | 概率统计篇答疑和总结：为什么会有欠拟合和过拟合？

## 拟合、欠拟合和过拟合

每种学习模型都有自己的假设和参数。虽然朴素贝叶斯和决策树都属于分类算法，但是它们各自的假设和参数都不相同。朴素贝叶斯的假设是贝叶斯定理和变量之间的独立性，而决策树的假设是集合的纯净程度或者混乱程度。

拟合模型其实就是指通过模型的假设和训练样本，推导出具体参数的过程。

是根据自变量的值来获取因变量的值，达到预测的效果。这种情况就是**适度拟合**（right fitting）。

有的时候拟合得到的模型过于简单，和训练样本之间的误差非常大，这种情况就是**欠拟合**（Under Fitting）。

拟合模型和训练样本之间的差异，我们就称为**偏差**（Bias）。

拟合得到的模型非常精细和复杂，和训练样本之间的误差非常小，我们称这种情况为**过拟合**（Over Fitting）。

训练样本和测试样本之间存在的差异，我们称为**方差**（Variance）。

## 如何处理欠拟合和过拟合？

欠拟合问题，产生的主要原因是特征维度过少，拟合的模型不够复杂，无法满足训练样本，最终导致误差较大。

过拟合问题产生的主要原因则是特征维度过多，导致拟合的模型过于完美地符合训练样本，但是无法适应测试样本或者说新的数据。