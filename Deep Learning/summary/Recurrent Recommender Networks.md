# Recurrent Recommender Networks

[论文原文]()

## Recurrent Deep Networks

LSTM模型：

![](res/84.jpg)

## RRN

框架：

![](res/rrn.jpg)

### User and Movie State

以用户空间为例：

![](res/85.jpg)

### Rating Emissions

rating包括两部分，静态和动态：

![](res/86.jpg)

### Rating Prediction

extrapolated states：take the latest observations as input, update the states and make predictions based on the newly updated states.

### Inference

![](res/87.jpg)

优化方法：subspace descent