---
title: '基于 BERTopic 与情感计算的学术投稿行为研究'
date: 2023-06-01
tags:
  - BERTopic
  - 情感分析
  - 学术传播
image:
  caption: ''
  focal_point: ''
  preview_only: false
---

省级课题，基于万维书刊网 CSSCI 期刊投稿评论建模同行评议议题。

<!--more-->

采集万维书刊网 CSSCI 期刊投稿评论约 6.3 万条；以 Sentence-BERT（all-mpnet-base-v2）向量化，用贝叶斯优化算法调优 BERTopic，聚类出「审稿歧视」「隐性拒稿」等 7 类核心议题；以 Fengshenbang 预训练模型量化情感，发现负面情绪占比 56.8%，揭示投稿行为的周期波动规律。
