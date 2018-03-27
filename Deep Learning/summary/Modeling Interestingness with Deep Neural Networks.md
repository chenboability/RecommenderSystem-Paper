# Modeling Interestingness with Deep Neural Networks

[论文原文](https://github.com/chenboability/RecommenderSystem-Paper/blob/master/Deep%20Learning/paper/Modeling%20interestingness%20with%20deep%20neural%20networks.pdf)

> 用户u看来文章a之后，为他推荐文章b

## 框架

![](res/128.jpg)

## Network Architecture

### Input Layer

每一个词one-hot编码+tri-letter(“#dog#”,->“#do”, “dog”, and “og#”.)

目的：
1、如果one-hot的字典库中没有出现的词，即OOV (out of vocabulary)，可以通过tri-letter区分

2、同一个词的不同时态、人称等变体，转换成相似的表达方式

### Convolutional Layer

窗口大小为3，对每一个词进行卷积

![](res/129.jpg)

### Max-pooling Layer

对所有词，从每一个维度进行max-pooling，一个维度留下一个最大的词（300维，300个词）

![](res/130.jpg)

### Fully-Connected Layers 𝐡 and 𝐲

![](res/131.jpg)

## Training the DSSM

pair-wise rank loss

![](res/132.jpg)
![](res/133.jpg)
![](res/134.jpg)