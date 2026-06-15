---
summary: 图模型将高维分布的分解编码为图结构：节点为随机变量，边为直接依赖关系，缺失边编码条件独立。两大家族为贝叶斯网络和马尔可夫网络。
tags: [machine-learning, probabilistic-models]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-basics-concepts-graphical-model.md
  - raw/machine-learning/2026-06-08-probabilistic-models-bayesian-network.md
---

# 图模型

## 定义

将高维联合分布的分解一一对应地编码为图结构：节点 = 随机变量，边 = 直接依赖关系，缺失边 = 条件独立。

## 关键点

**贝叶斯网络**：有向无环图，分解规则：
$$p(X_1, \dots, X_d) = \prod_{i=1}^d p(X_i | PA_{X_i}^{\mathcal{G}})$$
条件独立性质：$X_i \perp \text{ND}_{X_i}^{\mathcal{G}} | PA_{X_i}^{\mathcal{G}}$（已知父节点后，与非后代节点独立）。

**马尔可夫网络**：无向图模型。

- 图模型的优势：只需为每个节点指定一个局部条件分布，而非一个巨大的联合模型。

## 关联概念

- [[hidden-markov-model]] — 特殊的贝叶斯网络，具有时序链结构
- [[gaussian-mixture-model]] — 含离散隐变量的贝叶斯网络
- [[factor-analysis]] — 含连续隐变量的贝叶斯网络
