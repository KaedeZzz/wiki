---
summary: 一种用 LLM 增量构建和维护个人知识库的模式，区别于 RAG 的"每次重新检索"，强调知识的编译和持续积累。
tags: [meta, knowledge-management, llm]
updated: 2026-06-08
sources:
  - raw/meta/2026-06-08-llm-wiki-pattern.md
---

# LLM Wiki 模式

## 定义

LLM Wiki 是一种个人知识管理模式：LLM 不只是在查询时检索原始文档，而是**增量构建并维护一个持久化的 wiki**——一组结构化、相互链接的 markdown 文件，位于用户和原始来源之间。每次新增来源时，LLM 阅读、提取关键信息、整合进现有 wiki，而非简单索引供日后检索。知识被编译一次并持续维护，而非每次查询时重新推导。

核心洞察：**wiki 是一个持久的、复利式增长的制品。** 交叉引用已经建好，矛盾已经标注，综合分析已经反映了所有已读来源。

## 关键点

- 人类负责三件事：投喂来源、提问、思考。LLM 负责其余一切（摘要、交叉引用、归档、记账）。
- wiki 随每次 ingest 和每次 query 越来越丰富，形成复利效应。
- 适用场景广泛：个人成长、学术研究、读书笔记、团队内部知识库、竞品分析、尽职调查等。
- 推荐搭配 Obsidian 使用（图谱视图、Dataview 插件、Marp 幻灯片）。
- 本质上是一个 git 仓库的 markdown 文件，天然具备版本历史和协作能力。

## 关联概念

- [[rag-vs-wiki]] — LLM Wiki 模式的提出正是为了解决 RAG 的"无积累"问题
- [[three-layer-architecture]] — LLM Wiki 的三层结构设计
- [[wiki-operations]] — wiki 的三个核心操作：Ingest / Query / Lint
- [[memex]] — 思想渊源，1945 年 Vannevar Bush 提出的个人知识存储愿景
