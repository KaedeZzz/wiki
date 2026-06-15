---
summary: 聚类是无监督学习任务，将数据点按相似性分组。K-means 使用硬分配迭代优化，Soft K-means 用概率化的软分配替代。
tags: [machine-learning, unsupervised]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-basics-concepts-clustering.md
  - raw/machine-learning/2026-06-08-expectation-maximisation-k-means-clustering.md
  - raw/machine-learning/2026-06-08-expectation-maximisation-soft-k-means-clustering.md
---

# 聚类

## 定义

将数据点分组，使同组点彼此相似度高于异组点。形式化为向量量化问题：选择分配规则 $x \to k(x)$ 和重建规则 $k \to \mathbf{m}^{(k)}$，最小化期望失真 $D = \sum_x P(x) \frac{1}{2}[\mathbf{m}^{(k(x))} - x]^2$。

## 关键点

**K-means**：将 $N$ 个数据点分入 $K$ 个簇，每簇由均值 $\mathbf{m}^{(k)}$ 参数化。
- 分配步：$r_k^{(n)} = 1$ 若 $k$ 是最近的均值，否则为 0。
- 更新步：$\mathbf{m}^{(k)} = \frac{\sum_n r_k^{(n)} x^{(n)}}{\sum_n r_k^{(n)}}$。
- 保证收敛，但无法表示簇的大小或形状。

**Soft K-means**：用概率化的软责任替代硬分配：
$$r_k^{(n)} = \frac{\exp(-\beta \, d(\mathbf{m}^{(k)}, x^{(n)}))}{\sum_{k'} \exp(-\beta \, d(\mathbf{m}^{(k')}, x^{(n)}))}$$

## 关联概念

- [[gaussian-mixture-model]] — 聚类的概率化推广，用 EM 算法训练
- [[expectation-maximisation]] — Soft K-means 可视为 EM 的特例
