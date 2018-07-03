# Learning Distributed Representations from Reviews for Collaborative Filtering

[论文原文]()

## Taming the Curse of Data Sparsity

克服数据的稀疏性带来的问题，方法有以下几种：

1. 在损失函数中添加正则化项；
2. 将矩阵分解放入概率框架，例如PMF；
3. 多任务学习

## 任务一： Rating Predict

基于矩阵分解：

![](res/1.jpg)

参数估计的损失函数：

![](res/2.jpg)

## 任务二：Review Modeling

![](res/3.jpg)

## 多任务目标

![](res/4.jpg)

## 模型一：BoWLF: Distributed Bag-of-Word

假设：review是词袋模型.故dui可以通过以下方式计算：

![](res/5.jpg)

## 模型二：LMLF: Recurrent Neural Network

假设：review每一个词保持词序，利用RNN（LSTM）语言模型.故dui可以通过以下方式计算：

![](res/7.jpg)

LSTM模型：

![](res/6.jpg)