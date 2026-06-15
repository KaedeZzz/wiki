---
summary: t-SNE 将高维空间中的距离转化为概率分布，用 KL 散度优化低维表示使其保持邻近关系。高维用高斯分布，低维用 t 分布。非线性但较慢。
tags: [machine-learning, dimensionality-reduction, visualisation]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-deep-learning-autoencoders-t-sne.md
---

# t-SNE

## 定义

t-Distributed Stochastic Neighbour Embedding（2008）。核心思想：高维空间中接近的点在低维空间中也应接近。

## 关键点

1. 高维空间：将点间距离概率化为高斯分布 $p_{i,j} = \frac{\exp(-\|x_i - x_j\|^2 / 2\sigma_i^2)}{\sum_{k \neq i} \exp(-\|x_i - x_k\|^2 / 2\sigma_i^2)}$
2. 低维空间：随机放置点，计算类似概率 $q_{i,j}$
3. 最小化 KL 散度 $D_{KL}(P \| Q)$

**t-SNE vs SNE**：高维用高斯分布，低维用 Student's t 分布（更重尾），缓解拥挤问题。

- $\sigma_i$ 通过迭代匹配目标困惑度（perplexity）确定。
- 困惑度的微小变化会显著改变可视化结果，需反复调试。
- 非线性，但**很慢**。

## 关联概念

- [[pca]] — 线性替代方案，快得多
- [[umap]] — 更快且质量更高的非线性替代方案
- [[autoencoder]] — 潜空间可视化的三种方法之一
