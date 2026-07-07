---
summary: 计算基础三点：CPU 的 fetch-decode-execute 循环通过 ALU/寄存器/控制单元实现指令流；Amdahl 定律揭示局部加速的整体上限；AI 是"能完成通常需要人类智能任务的计算系统"的宽泛定义。
tags: [computer-science, fundamentals]
updated: 2026-07-06
sources:
  - raw/computer-science/2026-07-06-amdahls-law.md
  - raw/computer-science/2026-07-06-architectures-cpu.md
  - raw/computer-science/2026-07-06-artificial-intelligence.md
---

# 计算基础

## 定义

一组关于**计算机体系结构、性能极限、AI 边界**的最基础概念集合。此页做速查笔记，不追求深度。

## 关键点

### CPU 的核心结构

中央处理器（CPU）负责从主存**取指令**（fetch）、**判断类型**（decode）、**执行**（execute）算术/逻辑运算。核心内部部件：

- **寄存器（Registers）**：极快的小容量存储，用于操作数与结果；含**程序计数器**（PC）等特殊寄存器
- **算术逻辑单元（ALU）**：执行加减、位运算、比较等
- **控制单元（Control）**：解析指令并驱动其他部件按序完成操作

这是**冯诺依曼模型**的核心；缓存、流水线、乱序执行、SIMD 等都是在此之上的性能优化层。

### Amdahl 定律

**核心洞察**：*Make the common case fast*——性能优化的收益上限受"被优化部分占总时间的比例"限制。设改进覆盖一段占比 $f$、加速比为 $s$：

$$t_{\text{new}} = t_{\text{old}}\left[(1-f) + \frac{f}{s}\right]$$

极限情形 $s\to\infty$（无限加速被优化部分）：$t_{\text{new}} \to (1-f)\,t_{\text{old}}$——**总加速比不超过 $1/(1-f)$**。

典型推论：

- 若并行化只覆盖 $f=0.9$，即使核数无限，最多加速 $10\times$
- 优化少见路径几乎不改善端到端时间
- 判断该优化什么之前，先**测量**热点比例（profiling）

Amdahl 也解释了为什么 GPU 加速对某些工作负载（如 CPU 密集的串行部分占大头）几乎无效。

### 人工智能

**宽定义**："能执行通常需要人类智能的任务（视觉感知、语音识别、决策等）的计算系统"。此定义故意宽泛，历史上覆盖：

- **符号 AI / 专家系统**（1960-80s）：规则、逻辑推理、搜索
- **统计机器学习**（1990s-2010s）：从数据学习模式，[[supervised-and-unsupervised-learning]]、[[loss-function]] 优化
- **深度学习 + 生成式**（2015-）：[[neural-network]]、注意力、大规模预训练

工程视角上"AI" 一词太宽，常被更准确的术语替代（ML、DL、LLM、生成式 AI 等），但作为学科名和产品分类仍普遍。

## 关联概念

- [[neural-network]] — 现代 AI 的主要范式
- [[supervised-and-unsupervised-learning]] — ML 的两大 paradigm
- [[gradient-descent]] — 训练 DL 模型的核心算法
