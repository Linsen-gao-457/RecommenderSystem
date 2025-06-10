# Table of Contents

- [Table of Contents](#table-of-contents)
- [推荐系统的基本概念](#推荐系统的基本概念)
- [推荐系统的链路](#推荐系统的链路)
- [推荐系统的AB测试](#推荐系统的ab测试)

# [推荐系统的基本概念](https://github.com/Linsen-gao-457/RecommenderSystem/blob/main/Slides/01_Basics_01.pdf)

Introduce little red book's recoomendation system -> 消费指标 -> 北极星指标 -> 实验流程


**消费指标**
以小红书为例的消费指标是 点击率、点赞率、收藏率、转发率、阅读完成率（引入阅读长度这个量）

**北极星指标**： 用户规模(daily active user, monthly active user)、消费、发布

**北极星指标 vs 消费指标**
北极星指标是指企业的业务方向；消费指标指的是用户行为端与产品的交互

**实验流程**
离线实验-小流量实验-全流量上线

# [推荐系统的链路](https://github.com/Linsen-gao-457/RecommenderSystem/blob/main/Slides/01_Basics_02.pdf)

推荐系统的整条链路由：召回-粗排-精排-重排

**召回**：用多条通道从几万篇笔记中取出几千篇

**粗排**: 用小规模的神经网络给几千篇笔记打分，选取出分数最高的几百篇

**精排**: 用大规模升级网络，给几百篇打分

**重排**: 用多样性测试（如MMR,DPP),从几百篇中选出几十篇并结合规则打散同标题笔记、插入广告、推广内容、更具生态要求调整排序

# [推荐系统的AB测试](https://github.com/Linsen-gao-457/RecommenderSystem/blob/main/Slides/01_Basics_03.pdf)

AB test(what\how) - 分桶 - 分层实验 - holdout -  实验推全 & 反转实验

AB test：
先做离线测试 在做小流量AB test再做全流量AB test

分桶的目的：有统计学意义，管理多个实验

分层：解决data不足的问题，其中同层互斥、不同层正交

holdout: 考察业务

实验推全： 一个实验成功就推全，上演叠加效应（可能diff不会那么赞也可能更好）

反转实验：推全层保留旧层用以观测一些迟滞性指标