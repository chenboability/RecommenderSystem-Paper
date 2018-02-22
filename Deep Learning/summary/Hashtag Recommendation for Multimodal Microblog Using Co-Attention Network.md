# Hashtag Recommendation for Multimodal Microblog Using Co-Attention Network

[论文原文](https://github.com/chenboability/RecommenderSystem-Paper/blob/master/Deep%20Learning/paper/Hashtag%20Recommendation%20for%20Multimodal%20Microblog%20Using%20Co-Attention%20Network.pdf)

## 模型

![](res/101.jpg)

## The Proposed Models

### Feature Extraction

#### Image feature extraction

将图片分割成N x N grid，然后对每一个块，利用VGGNet提取D-dimensional feature vector

#### Text feature extraction

对博客文本利用lstm提取特征

![](res/102.jpg)

### Co-Attention Network

#### Tweet-guided visual attention

![](res/103.jpg)

#### Image-guided textual attention

![](res/104.jpg)

![](res/105.jpg)

#### Stacked co-attention network

for the k-th (where k is greater than or equal to 2) coattention layer, we respectively compute the distribution of visual and textual attention and
generate a new representation for the input image and text
based on the attention probability.

![](res/106.jpg)

### Prediction

该博客适合标签a的概率：

![](res/107.jpg)

### Training

目标函数：

![](res/108.jpg)