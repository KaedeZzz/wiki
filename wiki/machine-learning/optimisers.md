---
summary: 基于梯度下降的高级优化器：归一化梯度下降、Nesterov 加速动量、ADAM（自适应矩估计），通过自适应学习率和动量加速收敛。
tags: [machine-learning, optimisation]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-optimisers-normalised-gradient-descent.md
  - raw/machine-learning/2026-06-08-optimisers-nesterov-accelerated-momentum.md
  - raw/machine-learning/2026-06-08-optimisers-adam.md
---

# 优化器

## 定义

在基本 [[gradient-descent]] 之上，高级优化器通过自适应学习率和动量策略加速收敛。

## 关键点

**归一化梯度下降**：用逐元素平方梯度归一化更新方向：
$$\theta_{t+1} = \theta_t - \alpha \frac{\mathbf{m}_{t+1}}{\sqrt{\mathbf{v}_{t+1}} + \epsilon}$$

**Nesterov 加速动量**：在动量预测的"未来位置"计算梯度，而非当前位置：
$$\mathbf{m}_{t+1} = \beta \cdot \mathbf{m}_t + (1-\beta) \frac{\partial L(\theta_t - \alpha \mathbf{m}_t)}{\partial \theta}$$

**ADAM（Adaptive Moment Estimation）**：结合动量和自适应学习率，维护梯度均值 $\mathbf{m}$ 和逐元素平方梯度 $\mathbf{v}$ 的指数移动平均，并做偏差修正：
$$\tilde{\mathbf{m}}_{t+1} = \frac{\mathbf{m}_{t+1}}{1-\beta^{t+1}}, \quad \tilde{\mathbf{v}}_{t+1} = \frac{\mathbf{v}_{t+1}}{1-\gamma^{t+1}}$$
$$\theta_{t+1} = \theta_t - \alpha \frac{\tilde{\mathbf{m}}_{t+1}}{\sqrt{\tilde{\mathbf{v}}_{t+1}} + \epsilon}$$

## 关联概念

- [[gradient-descent]] — 所有优化器的基础
- [[neural-network]] — 优化器的主要使用场景
