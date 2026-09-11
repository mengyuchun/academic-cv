---
title: ''
summary: ''
date: 2024-09-01
type: landing

sections:
  - block: resume-biography-3
    content:
      username: me
      text: ''
      headings:
        about: About
        education: Education
        interests: Research Interests
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
      title: Research
      text: |-
        I work at the intersection of publishing studies, computational communication, and digital humanities. My current research examines the multimodal computational communication of micro-dramas, paradigm shifts in publishing-history scholarship, and AI and copyright governance.

        Methodologically, I combine qualitative content analysis with NLP and multimodal methods such as BERTopic, Sentence-BERT, and LoRA/QLoRA fine-tuning of multimodal models for ancient-Chinese document layout analysis.

        I am open to PhD opportunities in publishing studies, book history, digital humanities, computational communication, and AI governance.
    design:
      columns: '1'
  - block: collection
    id: publications
    content:
      title: Selected Publications
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
      title: Research Projects
      filters:
        folders:
          - projects
    design:
      view: article-grid
      columns: 2
  - block: collection
    id: talks
    content:
      title: Conference Talks
      filters:
        folders:
          - events
    design:
      view: card
---
