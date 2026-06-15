---
summary: LLM Wiki 的三层架构：raw sources（不可变原始来源）、wiki（LLM 维护的结构化知识层）、schema（操作规范文档）。
tags: [meta, architecture]
updated: 2026-06-08
sources:
  - raw/meta/2026-06-08-llm-wiki-pattern.md
---

# 三层架构

## 定义

LLM Wiki 由三个层次组成，各自职责分明：

1. **Raw Sources（原始来源层）**：用户策展的源文档集合——文章、论文、图片、数据文件。不可变，LLM 只读不写。这是事实来源（source of truth）。
2. **Wiki（知识层）**：LLM 生成并维护的 markdown 文件目录——摘要、实体页、概念页、对比分析、综述。LLM 完全拥有此层，负责创建、更新、维护交叉引用和一致性。用户阅读，LLM 书写。
3. **Schema（规范层）**：一份告诉 LLM wiki 结构、约定和工作流的文档（如 Claude Code 的 CLAUDE.md、Codex 的 AGENTS.md）。这是关键配置文件——它使 LLM 成为有纪律的 wiki 维护者而非通用聊天机器人。用户和 LLM 随时间共同演化此文档。

## 关键点

- 三层之间有清晰的读写权限划分：raw 只读、wiki LLM 读写、schema 人机共写。
- Schema 是使模式可复现的关键——没有它，LLM 只是在聊天，有了它，LLM 是一个有规范的知识工程师。
- 两个特殊文件辅助导航：`index.md`（内容导向的目录）和 `log.md`（时间线式的操作日志）。

## 关联概念

- [[llm-wiki-pattern]] — 此架构所服务的整体模式
- [[wiki-operations]] — 在此架构上执行的三个操作
