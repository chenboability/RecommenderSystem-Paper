# SoRec: Social Recommendation Using Probabilistic Matrix Factorization

[论文原文]()

> 文章思路：结合社交关系和MF，预测用户评分；利用社交关系，为新用户提供参考，解决冷启动问题。

社交图的示例如下图a所示（有向图），边的权值表示用户的信任程度，该图可以用m*m矩阵形式表示。原始的用户打分矩阵如b所示（用户4是新用户），预测的打分矩阵如c所示：

![](res/13.jpg)

## Social Network Matrix Factorization

社交网络的条件分布：

![](res/14.jpg)

user and factor feature vectors上的0均值的spherical Gaussian priors：

![](res/15.jpg)

贝叶斯推理：

![](res/16.jpg)

![](http://latex.codecogs.com/gif.latex?\{c_{ik}})一般是用户显式指定的。由于社交网络图中不同用户信任值的标准不一样，如出边很多的节点信任值应该适当降低；入边很多的节点信任值应该适当身高。所以，上式可以改成：

![](res/17.jpg)

## User-Item Matrix Factorization

同理如下：

![](res/18.jpg)

![](res/19.jpg)

![](res/20.jpg)

## Matrix Factorization for Social Recommendation

图模型：

![](res/SNPMF.jpg)

log后的后验分布如下：

![](res/21.jpg)

最大化上式，即最小化平方和误差（sum-of-squared-errors），如下：

![](res/22.jpg)

可以通过梯度下降，求得局部最小值。



