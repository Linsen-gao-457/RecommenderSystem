# Table of Contents

- [Table of Contents](#table-of-contents)
- [基于物品的协同过滤（ItemCF）](#基于物品的协同过滤itemcf)
  - [IntemCF theory](#intemcf-theory)
  - [The process of ItemCF](#the-process-of-itemcf)
- [Swing召回通道](#swing召回通道)
- [基于用户的协同过滤（UserCF）](#基于用户的协同过滤usercf)
- [离散特征处理](#离散特征处理)
- [矩阵补充模型 Matrix Coompletion](#矩阵补充模型-matrix-coompletion)
- [双塔模型 two-tower model：模型和训练](#双塔模型-two-tower-model模型和训练)
- [双塔模型 two tower model: 正负样本](#双塔模型-two-tower-model-正负样本)
- [双塔模型：线上召回和更新](#双塔模型线上召回和更新)
- [双塔模型 自监督学习](#双塔模型-自监督学习)

# [基于物品的协同过滤（ItemCF）](https://github.com/Linsen-gao-457/RecommenderSystem/blob/main/Slides/02_Retrieval_01.pdf)

## IntemCF theory

怎么找到相似的物品：知识图谱，用户的行为

ItemCF Asssumption: 用户喜欢一个物品，也会喜欢另一个物品

量化相似度：不加权，加权

## The process of ItemCF

index: user -> Item

Index: item -> item

why index?
避免枚举，节约时间

找到用户感兴趣的n,找到每个物品相似的TOP k物品，然后找到Top-k相似，列出TOP

# [Swing召回通道](https://github.com/Linsen-gao-457/RecommenderSystem/blob/main/Slides/02_Retrieval_02.pdf)

目的:考虑到社交群体-》reduce dependence on the ground

定义重合度 -> 减低重合度（ItemCF想要做的更精准，降低social connection对相似度带来的影响）

# [基于用户的协同过滤（UserCF）](https://github.com/Linsen-gao-457/RecommenderSystem/blob/main/Slides/02_Retrieval_03.pdf)

 根据用户相似度做推荐：
 1. 找到相似笔记
 2. 关注作者的重合度

 降低热门笔记权重， 如何计算用户之间的相似度(类似于ItemCF的Swing)

 # [离散特征处理](https://github.com/Linsen-gao-457/RecommenderSystem/blob/main/Slides/02_Retrieval_04.pdf)

 Onehot, embedding -> relationship between onehot and embedding

 # [矩阵补充模型 Matrix Coompletion](https://github.com/Linsen-gao-457/RecommenderSystem/blob/main/Slides/02_Retrieval_05.pdf)

 矩阵补充就是用绿色的格子做训练去预测灰格子。


 Approximate Nearest Neighbor Search 和  Nearset Neighbor Search:

 Approximate nearest neighbor search can narrorw down a slice of users into a vector instead of using every single vector to search.

 Matrix Completion 在实践中的效果并不好，因为负样本曝光之后，没有点击，交互等操作

 # [双塔模型 two-tower model：模型和训练](https://github.com/Linsen-gao-457/RecommenderSystem/blob/main/Slides/02_Retrieval_06.pdf)

 双塔模型就是融合了user ID, item ID, it combine different featuresa of the model(discrete and continuous feature)

 three training methods of 双塔模型: point wise, pairwise, listwise.

# [双塔模型 two tower model: 正负样本](https://github.com/Linsen-gao-457/RecommenderSystem/blob/main/Slides/02_Retrieval_07.pdf)

how to define negative sample; easy negative, hard negative; false

召回模型的目的是找到用户感兴趣的物品，reranker 是排序，所以曝光未点击的物品可以作为负样本

# [双塔模型：线上召回和更新](https://github.com/Linsen-gao-457/RecommenderSystem/blob/main/Slides/02_Retrieval_08.pdf)

In a two-tower model, item embeddings are usually precomputed, while user embedding are computed online in real time.

Why do we need both full and incremental updates？

In practice, companies often combine full and incremental updates:

- Full updates periodly reflesh embedding to ensure quality and consistency.
- Incremental updates capture the latest user behaviour and item changes, ensuring the system remains up-to-date and responsive in real time.

企业是两者结合，全量效果好，增量更新捕捉实时性

# [双塔模型 自监督学习](https://github.com/Linsen-gao-457/RecommenderSystem/blob/main/Slides/02_Retrieval_09.pdf)

Self-supervised learning helps alleviate the high-frequency item problem in recommendation systems. 

In typical user behavior data, head items appear very  frequently, so the model easily learns good representations for them. However, tail items have few interactions, so the model struggles to learn meaningful representations for these long-tail items.

By using self-supervised learning, we can generate additional training signals to better learn robust representations for both head and tail items, even when explicit interaction data is sparse.

There are several ways to reshape features:
1. random mask
2. drop out
3. complementary learning
4. mask related features
