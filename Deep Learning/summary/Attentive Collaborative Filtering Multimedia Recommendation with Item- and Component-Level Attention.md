# Attentive Collaborative Filtering: Multimedia Recommendation with Item- and Component-Level Attention

[论文原文](https://github.com/chenboability/RecommenderSystem-Paper/blob/master/Deep%20Learning/paper/Attentive%20Collaborative%20Filtering%20Multimedia%20Recommendation%20with%20Item-%20and%20Component-Level%20Attention.pdf)

> attention-based CF

## PRELIMINARIES

### Latent Factor Models

point-wise loss

![](res/23.jpg)

缺点：applying SVD in implicit feedback domain raises
difficulties due to the high portion of unobservable data.

### Bayesian Personalized Ranking (BPR)

pair-wise loss

![](res/24.jpg)

## ATTENTIVE COLLABORATIVE FILTERING

### General Framework

![](res/acf.jpg)

目标函数（从BPR借鉴，对ui进行改进）：

![](res/25.jpg)

其中![](http://latex.codecogs.com/gif.latex?\alpha(i,j))表示用户i对物品j的兴趣度，即item-级的attention。component-级的attention也和![](http://latex.codecogs.com/gif.latex?\alpha(i,j))有关。

评分预测：

![](res/26.jpg)

模型的解释（与Neighborhood Models关系）：

![](res/27.jpg)

因为the weights should be highly dependent to the user and the item content，因此作者设计了一个动态计算用户相关的权值计算方法。

模型的基本思路：

对于每一个物品l，将物品的第m部分（如图片的第m块或者视频的第m帧）以及用户ui作为component-子网络输入，得到![](http://latex.codecogs.com/gif.latex?\beta(l,m))作为该部分的权值，然后对物品的每一部分进行加权求和。然后，结合ui，vl，pl以及物品l子网络的结果，计算![](http://latex.codecogs.com/gif.latex?\alpha(i,l))作为用户i对物品l的权值，然后对用户i是所有物品进行加权求和。

### Item-Level Attention

权值![](http://latex.codecogs.com/gif.latex?\alpha)的计算，利用一个两层网络：

![](res/28.jpg)

然后用一个softmax函数：

![](res/29.jpg)

### Component-Level Attention

权值![](http://latex.codecogs.com/gif.latex?\beta)的计算，同样是一个两层网络，最后也是用一个softmax函数：：

![](res/30.jpg)