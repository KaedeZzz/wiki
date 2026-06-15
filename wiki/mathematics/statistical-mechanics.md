---
summary: 统计力学通过最大熵原理将能量函数与概率分布联系起来，导出 Boltzmann 分布，并与贝叶斯推断存在深层对应。
tags: [mathematics, probability, statistical-mechanics]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-probability-theory-statistical-mechanicsprobability-of-energy-states.md
  - raw/mathematics/2026-06-09-probability-theory-statistical-mechanicsising-model.md
  - raw/mathematics/2026-06-09-probability-theory-statistical-mechanicsenergy-function.md
  - raw/mathematics/2026-06-09-probability-theory-statistical-mechanicsenergy-of-parameters.md
---

# 统计力学

## 定义

基于热力学第一、第二定律（能量守恒、熵最大化），在能量约束下最大化熵：

$$\max_P S[P] = -\sum_\sigma P(\sigma)\log P(\sigma) \quad \text{s.t.} \quad \sum_\sigma P(\sigma)=1,\; \sum_\sigma E(\sigma)P(\sigma) = U$$

用 Lagrange 乘子法求解得 **Boltzmann 分布**：

$$P(\sigma) = \frac{e^{-\beta E(\sigma)}}{Z}, \quad Z = \sum_\sigma e^{-\beta E(\sigma)}$$

其中 $\beta = 1/T$（逆温度），$Z$ 为配分函数。

## 关键点

### Ising 模型

磁性原子 $\sigma_i = \pm 1$，仅考虑邻居相互作用的系统能量：

$$E(\sigma) = -\sum_{i,j} J_{ij} \sigma_i \sigma_j$$

扩展 Ising 模型加入外场项 $-\sum_i h_i \sigma_i$。

### 与贝叶斯推断的对应

定义参数的"能量"$E(\theta) = -\log P(D|\theta) - \log P(\theta)$，则 $e^{-E(\theta)}/Z \propto P(\theta|D)$，即后验分布正是 Boltzmann 形式。

## 关联概念

- [[probability-foundations]] — 概率分布的公理基础
- [[estimation-theory]] — 贝叶斯推断与能量最小化的对应
- [[graphical-model]] — Ising 模型是马尔可夫随机场的经典实例
