# Probabilistic Matrix Factorization

[论文原文]()

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

## Automatic Complexity Control for PMF Models


