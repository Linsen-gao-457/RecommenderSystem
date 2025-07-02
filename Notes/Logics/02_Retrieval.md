# Table of Contents

- [Table of Contents](#table-of-contents)
- [基于物品的协同过滤（ItemCF）](#基于物品的协同过滤itemcf)
  - [IntemCF theory](#intemcf-theory)
  - [The process of ItemCF](#the-process-of-itemcf)
- [Swing召回通道](#swing召回通道)
- [基于用户的协同过滤（UserCF）](#基于用户的协同过滤usercf)
- [离散特征处理](#离散特征处理)
- [Matrix Coompletion](#matrix-coompletion)

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

# Swing召回通道

目的:考虑到社交群体-》reduce dependence on the ground

定义重合度 -> 减低重合度

# 基于用户的协同过滤（UserCF）

 根据用户相似度做推荐：
 1. 找到相似笔记
 2. 关注作者的重合度

 降低热门笔记权重， 如何计算用户之间的相似度

 # 离散特征处理

 Onehot, embedding -> relationship between ONEhot and embedding

 # Matrix Coompletion

 矩阵补充就是用绿色的格子做训练去预测灰格子。

 交叉熵（分类）> 回归函数

 Nearest Neighbor Search 和 Neighbor Search

 Matrix Completion 在实践中的效果并不好，因为负样本曝光之后，没有点击，交互等操作

 