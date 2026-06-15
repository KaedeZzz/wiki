---
summary: Zipf 定律：在文本集合中，任何词的频率与其在频率表中的排名成反比。
tags: [machine-learning, nlp, statistics]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-text-models-zipf's-law.md
---

# Zipf 定律

## 定义

在文本集合中，任何词的频率与其在频率表中的排名成反比：频率 $\propto 1/\text{rank}$。

## 关键点

- 这意味着少数高频词占据大部分出现次数，而大量低频词各自很少出现（长尾分布）。
- 对 NLP 中的词汇表设计、子词分词、频率编码等有直接影响。

## 关联概念

- [[supervised-and-unsupervised-learning]] — 文本分类等 NLP 任务的统计基础
