---
summary: 梯度下降是通过沿损失函数梯度反方向迭代更新参数来最小化损失的优化算法，SGD 通过使用 mini-batch 引入噪声以逃离局部最小值并降低计算开销。
tags: [machine-learning, optimisation]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-basics-concepts-gradient-descent.md
  - raw/machine-learning/2026-06-08-basics-concepts-stochastic-gradient-descent.md
  - raw/machine-learning/2026-06-08-basics-theories-gradient-momentum.md
---

# 梯度下降

## 定义

迭代优化算法：初始化 $\theta^{(0)}$，每步计算梯度 $g = \frac{\partial L}{\partial \theta}$，更新 $\theta^{(i+1)} = \theta^{(i)} - \alpha g$，其中 $\alpha$ 为学习率。重复直到收敛。

## 关键点

**随机梯度下降（SGD）**：不对全部数据计算梯度，而是用 mini-batch $\mathcal{B}_t$：
$$g = \sum_{i \in \mathcal{B}_t} \frac{\partial L}{\partial \theta}$$
优势：能逃离局部最小值，计算开销更低。缺点：不在传统意义上收敛，需要学习率调度。

**动量（Momentum）**：加入速度记忆项，使更新沿一致方向运动：
$$\mathbf{m}_{t+1} = \beta \cdot \mathbf{m}_t + (1-\beta) \sum_{i \in \mathcal{B}_t} \frac{\partial L}{\partial \theta}$$
$$\theta_{t+1} = \theta_t - \alpha \cdot \mathbf{m}_{t+1}$$

## 关联概念

- [[optimisers]] — 基于梯度下降的高级优化器（ADAM、Nesterov 等）
- [[loss-function]] — 梯度下降所优化的目标
- [[regularisation]] — 修改损失函数以改善泛化
