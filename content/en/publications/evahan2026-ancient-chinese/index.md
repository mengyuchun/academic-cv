---
title: 'A Parameter-Efficient and Data-Centric Framework for Ancient Chinese Text Recognition and Layout Analysis'

authors:
  - me

date: '2026-05-11T00:00:00Z'
publishDate: '2026-05-11T00:00:00Z'

publication_types: ['paper-conference']

publication:
  name: "Proceedings of LT4HALA 2026 (LREC 2026 Workshop)"
  short_name: "LT4HALA 2026"

peer_reviewed: true
open_access: true

abstract: >-
  This paper presents the system developed for the EvaHan 2026 shared task on Ancient Chinese OCR and Layout Analysis. Participating in the Closed Track, we propose a highly parameter-efficient, data-centric framework based on the Qwen2.5-VL-7B-Instruct multimodal large language model (MLLM). While the official baseline utilizes the same backbone architecture, our approach significantly outperforms it by integrating orientation-aware image preprocessing and expert-constrained adaptive prompt engineering. We employed Low-Rank Adaptation (LoRA) with a minimal rank configuration (Rank=16) to train three independent, task-specific adapters. Our system achieved exceptional results, recording an Overall score of 0.9703 and an F1-score of 97.19% on printed text recognition (Task A)—effectively halving the baseline’s Character Error Rate. On handwritten texts (Task C), we maintained a highly competitive 90.18% F1-score. Furthermore, our model achieved significant progress in layout analysis (Task B), surpassing the baseline’s Macro F1 by 172% (0.4162 vs. 0.1530) and mAP by 37%. These results underscore that embedding explicit document structure and semantic constraints into MLLMs is more effective than simply scaling model parameters.

summary: A LoRA-based, data-centric framework for ancient-Chinese OCR and layout analysis, halving the baseline character error rate and lifting layout Macro F1 by 172%.

tags:
  - Ancient Chinese
  - Layout Analysis
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
