#### Table of Contents

- [多目标排序模型](#多目标排序模型)
- [Multi-gate Mixture-of-Experts(MMoE)](#multi-gate-mixture-of-expertsmmoe)
- [预估分数的融合](#预估分数的融合)
- [视频播放建模](#视频播放建模)
- [排序模型的特征](#排序模型的特征)
- [粗排](#粗排)

# [多目标排序模型](https://github.com/Linsen-gao-457/RecommenderSystem/blob/main/Slides/03_Rank_01.pdf)

排序的多目标模型，对负样本进行sub-sampling，然后再使用校准公式，得到结果

# [Multi-gate Mixture-of-Experts(MMoE)](https://github.com/Linsen-gao-457/RecommenderSystem/blob/main/Slides/03_Rank_02.pdf)

What's Multi-gate Mixture-of-Expert

How to avoid polarization problem in MMoE(dropout)

# [预估分数的融合](https://github.com/Linsen-gao-457/RecommenderSystem/blob/main/Slides/03_Rank_03.pdf)

differnet kinds of 融合分数公式
- 简单加权和
- 不同分数融合预测
- 视频平台预测融合分数

# [视频播放建模](https://github.com/Linsen-gao-457/RecommenderSystem/blob/main/Slides/03_Rank_04.pdf)

Youtube 对视频时长的预估

视频完成播放的预估建模
- 回归
- 二元分类
- 长短视频完播率调整

# [排序模型的特征](https://github.com/Linsen-gao-457/RecommenderSystem/blob/main/Slides/03_Rank_05.pdf)

- 用户画像
- 物品画像
- 统计特征
- 产品特征
- 特征处理

特征覆盖率，特征工程解决，召回和排序的pipeline服务器

# [粗排](https://github.com/Linsen-gao-457/RecommenderSystem/blob/main/Slides/03_Rank_06.pdf)

三塔模型（粗排）之前的模型是精排

