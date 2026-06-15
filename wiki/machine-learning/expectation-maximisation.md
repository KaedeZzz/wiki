---
summary: EM 算法通过交替执行 E-step（估计隐变量后验）和 M-step（最大化辅助函数更新参数）来迭代优化含隐变量模型的似然，每次迭代保证似然不减。
tags: [machine-learning, probabilistic-models, optimisation]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-expectation-maximisation-expectation-maximisation-(em).md
  - raw/machine-learning/2026-06-08-expectation-maximisation-derivation-of-em-algorithm,-4f10-handout.md
  - raw/machine-learning/2026-06-08-expectation-maximisation-auxiliary-function.md
---

# 期望最大化算法（EM）

## 定义

EM 算法交替进行两步，迭代求解含隐变量的极大似然估计：
- **E-step**：用当前参数计算隐变量的后验分布：$q_i^{(t+1)}(z_i) = p(z_i|x_i, \theta^{(t)})$
- **M-step**：最大化辅助函数（即 ELBO）更新参数：$\theta^{(t+1)} = \arg\max_\theta Q(\theta, \theta^{(t)})$

其中辅助函数：$Q(\theta, \theta^{(t)}) = \sum_i \sum_{z_i} p(z_i|x_i, \theta^{(t)}) \log p(x_i, z_i|\theta)$

## 关键点

- 核心性质：$\mathcal{L}(\theta^{(t+1)}) \geq \mathcal{F}(q^{(t+1)}, \theta^{(t+1)}) \geq \mathcal{F}(q^{(t+1)}, \theta^{(t)}) = \mathcal{L}(\theta^{(t)})$，保证收敛到局部最优。
- EM 用软概率分配替代硬标签分配，避免了梯度下降中学习率振荡的稳定性问题。
- 连续隐变量情形：辅助函数变为积分形式 $Q = \int p(z|x, \theta^{(t)}) \log p(x, z|\theta) dz$。

## 关联概念

- [[evidence-lower-bound]] — EM 实际优化的目标
- [[gaussian-mixture-model]] — EM 的经典应用
- [[clustering]] — K-means 可视为 EM 的硬分配特例
