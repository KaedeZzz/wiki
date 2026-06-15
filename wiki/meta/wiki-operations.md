---
summary: LLM Wiki 的三个核心操作：Ingest（投喂来源并编译进 wiki）、Query（从 wiki 检索回答）、Lint（健康检查并修复）。
tags: [meta, workflow]
updated: 2026-06-08
sources:
  - raw/meta/2026-06-08-llm-wiki-pattern.md
---

# Wiki 操作

## 定义

LLM Wiki 模式定义了三个核心操作，覆盖知识的输入、输出和维护。

## 关键点

### Ingest（投喂）
用户将新来源放入 raw 目录并告知 LLM 处理。典型流程：LLM 阅读来源 → 与用户讨论要点 → 在 wiki 中写入摘要页 → 更新索引 → 更新相关实体和概念页 → 在日志中追加条目。一个来源可能触及 10-15 个 wiki 页面。可逐条精细投喂，也可批量投喂。

### Query（查询）
用户对 wiki 提问。LLM 搜索相关页面、阅读并综合回答，附带引用。回答形式可以多样：markdown 页、对比表、幻灯片（Marp）、图表（matplotlib）。关键洞察：**好的回答可以归档为新的 wiki 页面**，使探索本身也形成知识积累。

### Lint（体检）
定期让 LLM 对 wiki 做健康检查：页面间矛盾、被新来源取代的过时声明、无入链的孤儿页、被提及但缺少自有页面的重要概念、缺失的交叉引用、可通过搜索填补的数据空白。LLM 擅长建议新的研究方向和需要寻找的来源。

## 关联概念

- [[llm-wiki-pattern]] — 这三个操作所服务的整体模式
- [[three-layer-architecture]] — 操作执行所依赖的三层结构
- [[rag-vs-wiki]] — Query 操作体现了 wiki 模式与 RAG 的核心区别
