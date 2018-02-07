# AutoSVD++: An Efficient Hybrid Collaborative Filtering Model via Contractive Auto-encoders

[论文原文](https://github.com/chenboability/RecommenderSystem-Paper/blob/master/Deep%20Learning/paper/AutoSVD%2B%2B.pdf)

## Latent Factor Models & Contractive Auto-encoders
### Latent Factor Models
#### Biased SVD

引入用户偏差和物品偏差：

![](res/48.jpg)

#### SVD++

引入隐式反馈：

![](res/49.jpg)

### Contractive Auto-encoders

![](res/50.jpg)

## PROPOSED METHODOLOGY

框架：

![](res/autoSVD.jpg)

### AutoSVD

利用CAE提取特征：

![](res/51.jpg)

预测得分：

![](res/52.jpg)

### AutoSVD++

![](res/53.jpg)