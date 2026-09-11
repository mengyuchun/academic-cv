---
title: ''
summary: ''
date: 2024-09-01
type: landing

sections:
  - block: resume-biography-3
    content:
      username: me-zh
      text: ''
      headings:
        about: 个人简介
        education: 教育背景
        interests: 研究兴趣
    design:
      background:
        gradient_mesh:
          enable: true
      name:
        size: md
      avatar:
        size: medium
        shape: circle
  - block: markdown
    content:
      title: 研究
      text: |-
        我的研究位于出版学、计算传播与数字人文的交叉地带。当前关注微短剧的多模态计算传播特征，用大语言模型量化出版史研究的范式变迁，以及人工智能与版权治理。

        在方法上，我将定性内容分析与 BERTopic、Sentence-BERT 等 NLP 及多模态方法结合，并具备多模态模型参数高效微调（LoRA/QLoRA）用于古籍版面分析的实践经验。

        目前正在寻求出版学、书籍史、数字人文、计算传播与人工智能治理方向的博士就读机会。
    design:
      columns: '1'
  - block: collection
    id: publications
    content:
      title: 学术成果
      filters:
        folders:
          - publications
        featured_only: true
    design:
      view: article-grid
      columns: 2
  - block: collection
    id: projects
    content:
      title: 研究项目
      filters:
        folders:
          - projects
    design:
      view: article-grid
      columns: 2
  - block: collection
    id: talks
    content:
      title: 会议交流
      filters:
        folders:
          - events
    design:
      view: card
---
