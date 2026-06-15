---
summary: RAG（检索增强生成）与 LLM Wiki 模式的核心区别：前者每次查询重新检索，后者将知识编译为持久化 wiki。
tags: [meta, rag, knowledge-management]
updated: 2026-06-08
sources:
  - raw/meta/2026-06-08-llm-wiki-pattern.md
---

# RAG vs Wiki

## 定义

RAG（Retrieval-Augmented Generation）和 LLM Wiki 是两种不同的 LLM + 文档交互范式。RAG 在查询时从原始文档检索相关片段再生成回答；LLM Wiki 则在来源加入时就将知识编译进持久化的结构化 wiki，查询时直接从 wiki 回答。

## 关键点

| 维度 | RAG | LLM Wiki |
|------|-----|----------|
| 知识何时处理 | 查询时（每次重新检索） | 投喂时（编译一次，持续维护） |
| 积累性 | 无——每次从零拼凑 | 有——wiki 随来源增加持续增长 |
| 跨文档综合 | 困难，需找到并拼接多个片段 | 自然，交叉引用在 ingest 时已建立 |
| 矛盾检测 | 不主动检测 | 在 ingest 时标注矛盾 |
| 典型产品 | NotebookLM、ChatGPT 文件上传 | Karpathy LLM Wiki 模式 |

- RAG 的核心问题：LLM 每次查询都在"从头发现知识"，没有积累。问一个需要综合五篇文档的微妙问题，每次都要重新找到并拼凑相关片段。
- LLM Wiki 的优势：知识被编译一次，交叉引用已建好，矛盾已标注，综合分析已反映所有已读来源。

## 关联概念

- [[llm-wiki-pattern]] — Wiki 模式的完整描述
- [[wiki-operations]] — Wiki 模式下的具体操作流程
