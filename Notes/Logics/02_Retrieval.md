# Table of Contents

- [Table of Contents](#table-of-contents)
- [基于物品的协同过滤（ItemCF）](#基于物品的协同过滤itemcf)
  - [IntemCF theory](#intemcf-theory)
  - [The process of ItemCF](#the-process-of-itemcf)

# [基于物品的协同过滤（ItemCF）](https://github.com/Linsen-gao-457/RecommenderSystem/blob/main/Slides/02_Retrieval_01.pdf)

## IntemCF theory

怎么找到相似的物品：知识图谱，用户的行为

量化相似度：不加权，加权

## The process of ItemCF

index: user -> Item

Index: item -> item

why index?
避免枚举，节约时间

找到用户感兴趣的n,找到每个物品相似的TOP k物品，然后找到Top-k相似，列出TOP 前列