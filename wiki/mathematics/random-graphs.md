---
summary: 随机图模型及其性质，包括 Erdős-Rényi 模型、配置模型与无标度网络。
tags: [mathematics, graph-theory]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-graph-theory-random-graphs.md
---
# 随机图

## 定义

随机图是按照某种概率规则生成的图，用作真实网络的理论基准模型。通过比较真实网络与随机图的性质差异，可以识别出网络中的非平凡结构。

## 关键点

### Erdős-Rényi 模型

$G(n, p)$ 模型：$n$ 个节点中每对节点独立地以概率 $p$ 连边。

- 度分布近似泊松分布：$P(k) \approx e^{-\langle k \rangle} \frac{\langle k \rangle^k}{k!}$，其中 $\langle k \rangle = p(n-1)$
- **巨分量相变**：当 $\langle k \rangle > 1$（即 $p > 1/n$）时，出现占总节点有限比例的巨连通分量
- 聚类系数 $C = p$，随 $n$ 增大趋于零（与真实网络不符）

### 配置模型

给定度序列 $(k_1, k_2, \dots, k_n)$，每个节点生成 $k_i$ 个"半边"（stub），随机配对形成完整边。

- 可精确控制度分布
- 用于检验"仅由度分布能解释多少网络性质"
- 模块度的零模型即基于配置模型

### 无标度网络

许多真实网络的度分布服从幂律：

$$P(k) \sim k^{-\gamma}, \quad \gamma \in (2, 3) \text{ 典型}$$

特征：少数"枢纽"（hub）节点拥有极高度数，对网络连通性至关重要。

- **Barabási-Albert 模型**：增长 + 优先连接机制生成幂律度分布
- 对随机故障鲁棒，但对针对枢纽的攻击脆弱

### 巨分量阈值

Erdős-Rényi 中 $p_c = 1/n$ 是巨分量出现的临界点。配置模型中等价条件为：

$$\frac{\langle k^2 \rangle}{\langle k \rangle} > 2$$

即度分布的二阶矩与一阶矩之比超过 2。

## 关联概念

- [[graph-fundamentals]] — 图的基本定义
- [[graph-properties]] — 聚类系数、模块度等性质在随机图中的理论值作为基准
