---
title: '面向古籍文本识别与版面分析的参数高效与以数据为中心的框架'

authors:
  - me-zh

date: '2026-05-11T00:00:00Z'
publishDate: '2026-05-11T00:00:00Z'

publication_types: ['paper-conference']

publication:
  name: "LT4HALA 2026（LREC 2026 工作坊）论文集"
  short_name: "LT4HALA 2026"

peer_reviewed: true
open_access: true

abstract: >-
  本文提出面向 EvaHan 2026 古籍 OCR 与版面分析评测任务的系统。参加封闭赛道，我们基于 Qwen2.5-VL-7B-Instruct 多模态大语言模型，提出一个高度参数高效、以数据为中心的框架。官方基线采用相同骨干架构，而我们的方法通过方向感知的图像预处理与专家约束的自适应提示工程显著超越基线。我们采用低秩适配（LoRA，Rank=16）训练三个独立的任务专用适配器。系统在印刷体文本识别（任务 A）上取得 0.9703 的总分和 97.19% 的 F1，将基线字符错误率大致减半；在手写文本（任务 C）上保持 90.18% 的高竞争力 F1；在版面分析（任务 B）上，Macro F1 较基线提升 172%（0.4162 对 0.1530），mAP 提升 37%。结果表明，将显式的文档结构与语义约束嵌入多模态大模型，比单纯扩大模型参数更有效。

summary: 基于 LoRA 的以数据为中心的古籍 OCR 与版面分析框架，将基线字符错误率大致减半，版面 Macro F1 提升 172%。

tags:
  - 古籍
  - 版面分析
  - LoRA

featured: true

hugoblox:
  ids:
    doi: 10.63317/4inrcp772rid

links:
  - type: pdf
    url: paper.pdf
  - type: url
    url: https://lrec.elra.info/lrec2026-ws-lt4hala-29

projects: []
---
