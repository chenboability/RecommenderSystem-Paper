# Collaborative Denoising Auto-Encoders for Top-N Recommender Systems

[论文原文](https://github.com/chenboability/RecommenderSystem-Paper/blob/master/Deep%20Learning/paper/Collaborative%20Denoising%20Auto-Encoders%20for%20Top-N%20Recommender%20Systems.pdf)

## Denoising Auto-Encoders

1、 classical auto-encoder

![](res/40.jpg)

2、 Denoising Auto-encoder (DAE)

![](res/41.jpg)

## CDAE
三个层：the input layer, the hidden layer and the output layer（单隐层结构）

结构如下：

![](res/CDAE.jpg)

第一步：将输入映射成低维的隐式表

![](res/42.jpg)

第二步：将低维的隐式表达恢复到原始输入空间

![](res/43.jpg)
![](res/44.jpg)

参数的学习：最小化重构误差

![](res/45.jpg)