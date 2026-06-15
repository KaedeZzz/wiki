---
summary: UMAP 用图结构（而非概率分布）表示高维和低维空间中的邻近关系，通过交叉熵优化低维表示。比 t-SNE 快且更好地保持全局结构。
tags: [machine-learning, dimensionality-reduction, visualisation]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-deep-learning-autoencoders-umap.md
---

# UMAP

## 定义

Uniform Manifold Approximation and Projection（2018）。核心思想类似 SNE——保持高维空间中的相似性到低维，但用**图**代替概率分布。

## 关键点

方法：
1. 对每个点找 $k$ 近邻（$k$ 是主要超参数）
2. 将邻居连接转为加权图：$v_{i,j} = \exp\left(-\frac{\max(0, d(x_i, x_j) - \rho_i)}{\sigma_i}\right)$
3. 对称化合并图：$w_{ij} = v_{i,j} + v_{j,i} - v_{i,j} \cdot v_{j,i}$（权重在 0 到 1 之间）
4. 在低维空间重复此过程
5. 用交叉熵比较两个邻接矩阵，梯度下降优化

- 比 [[t-sne]] 快但比 [[pca]] 慢。
- 质量很高，善于保持相对位置。
- 增加近邻数使模型行为更可预测（更好的潜空间）。
- 不需要标准化，计算更快。

## 关联概念

- [[t-sne]] — 类似思想但用概率分布，更慢
- [[pca]] — 线性替代方案，最快
- [[autoencoder]] — 潜空间可视化的使用场景
