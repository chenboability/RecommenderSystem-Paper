# Probabilistic Matrix Factorization

[论文原文](https://github.com/chenboability/RecommenderSystem-Paper/blob/master/Matrix%20Factorization/paper/Probabilistic%20Matrix%20Factorization.pdf)

CF的弊端：

- 大数据集下，可拓展性差
- 对于评分少的用户（冷启动），推荐效果差

## Probabilistic Matrix Factorization (PMF)

PMF的图模型：

![](res/pmf.jpg)

带高斯噪声的概率线性模型：

![](res/2.jpg)

![](res/3.jpg)

后验概率：

![](res/4.jpg)

最大化上式等价于最小化下式：

![](res/5.jpg)

求解方法可以通过对U和V执行梯度下降。为了避免预测的评分值超过评分允许范围，应该进行归一化：

![](res/6.jpg)

其中，g(x)为逻辑函数，g(x) = 1/(1+exp(-x))

## Constrained PMF

图模型如下：

![](res/cpmf.jpg)

用户i的特征向量：

![](res/7.jpg)

其中，I是indicator matrix，当用户i对物品j评分过时，![](http://latex.codecogs.com/gif.latex?\{I_{ij}=1})，否则等于0。分母起到计数的作用。W是latent similarity constraint matrix，W的第i列，表示该用户历史评分的物品影响。
**因此，有着相似历史评分的用户，他们的特征向量有着相似的先验分布。**
Y是这先验分布均值的偏差（在PMF下，由于先验分布均值=0，因此U=Y）

因此，条件分布如下：

![](res/8.jpg)

![](res/9.jpg)

因此，最小化下面的式子：

![](res/12.jpg)
