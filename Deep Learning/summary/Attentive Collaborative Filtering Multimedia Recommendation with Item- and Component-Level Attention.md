# Attentive Collaborative Filtering: Multimedia Recommendation with Item- and Component-Level Attention

> attention-based CF

## PRELIMINARIES
### Latent Factor Models
![](res/23.jpg)
缺点：applying SVD in implicit feedback domain raises
difficulties due to the high portion of unobservable data.
### Bayesian Personalized Ranking (BPR)
![](res/24.jpg)

## ATTENTIVE COLLABORATIVE FILTERING
### General Framework
![](res/acf.jpg)

目标函数（从BPR借鉴）：
![](res/25.jpg)

评分预测：

![](res/26.jpg)

模型的解释（与Neighborhood Models关系）：

![](res/27.jpg)

因为the weights should be highly dependent to the user and the item content，因此作者设计了一个动态计算用户相关的权值计算方法。

### Item-Level Attention
权值![](http://latex.codecogs.com/gif.latex?\alpha)的计算，利用一个两层网络：

![](res/28.jpg)

![](res/29.jpg)

### Component-Level Attention
权值![](http://latex.codecogs.com/gif.latex?\beta)的计算，同样是一个两层网络：

![](res/30.jpg)