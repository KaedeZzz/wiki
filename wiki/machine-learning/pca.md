---
summary: PCA 将数据投影到协方差矩阵最大特征向量（主成分）方向，实现线性降维。快速、可解释，但无法处理非线性数据。
tags: [machine-learning, dimensionality-reduction]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-deep-learning-autoencoders-principal-component-analysis.md
---

# 主成分分析（PCA）

## 定义

将数据投影到协方差矩阵的最大特征向量方向（主成分），本质是奇异值分解。

## 关键点

- 计算：求协方差矩阵 → 求特征值和特征向量 → 投影到前 $k$ 个主成分。
- 复杂度 $O(nd^2 + d^3)$，随数据量线性增长，非常快。
- 特征值表示每个潜空间维度的重要性，提供可解释性。
- 局限：只能处理线性结构，非线性数据需 [[t-sne]] 或 [[umap]]。

## 关联概念

- [[autoencoder]] — PCA 是线性自编码器的特例
- [[factor-analysis]] — 当噪声各向同性时，因子分析退化为概率 PCA
- [[t-sne]] — 非线性降维可视化方法
- [[umap]] — 基于图的非线性降维方法
