# Kaggle - Quora Insincere Questions Classification

比赛链接：<https://www.kaggle.com/c/quora-insincere-questions-classification>

### 比赛为文本二分类比赛，判断问题的真实性（sincere/insincere）

### 代码内容包括：
- 文本预处理部分，使得embedding最大程度将文本向量化。
- 对文本序列化，变成可输入网络结构
- 设计网络：包含CNN、LSTM等
- 尝试k-Fold交叉验证

### 更新：
- 在之前对CNN的学习中，都提到CNN对于学习文本局部特征，在分类问题中表现甚好，但是本人在比赛期间CNN一直成绩不佳，后续也没有使用。
- 今日重新对CNN进行了学习，并回顾了当时比赛的网络结构，发现了比赛时使用CNN的问题所在，即CNN在卷积过程中是分为1D与2D结构的，我使用了1D的结构，对于每一个文本来说，在卷积时仅仅是对单词向量做了卷积处理，而并未将多个词语进行卷积，因此并未获得更高维度的特征向量，而是在不断的对单词向量进行卷积处理，因此没有起到对后续分类的特征提取效果。
