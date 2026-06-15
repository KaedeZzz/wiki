---
summary: 机器学习的三大范式：监督学习（从标注数据学习输入到输出的映射）、无监督学习（从无标注数据中发现结构）、强化学习（通过奖励信号学习最优行为策略）。
tags: [machine-learning, basics]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-basics-concepts-supervised-&-unsupervised-learning.md
  - raw/machine-learning/2026-06-08-basics-concepts-generation-of-training-data.md
  - raw/machine-learning/2026-06-08-basics-concepts-training-and-loss-minimisation.md
---

# 监督学习与无监督学习

## 定义

给定感知输入序列 $x_1, x_2, \dots$：

- **监督学习**：给定期望输出 $y_1, y_2, \dots$，目标是学习在新输入下产生正确输出。
- **无监督学习**：目标是建立 $x$ 的模型，用于推理、决策、预测等。
- **强化学习**：机器产生动作 $a_1, a_2, \dots$ 影响环境状态，接收奖励 $r_1, r_2, \dots$，目标是最大化长期奖励。

## 关键点

- 监督学习训练数据 $\mathcal{D} = \{(x_i, y_i)\}$ 是从联合分布 $p(\omega, x)$ 中采样得到的。
- 训练目标是最小化期望损失（actual loss）$\mathcal{L}_{act}$，但由于真实分布未知，实际优化的是经验损失（empirical loss）。
- 训练损失和测试损失可以不同；关键是关注未见数据上的表现。

## 关联概念

- [[loss-function]] — 训练的优化目标
- [[gradient-descent]] — 最小化损失的基本方法
- [[regularisation]] — 缩小泛化差距的方法
- [[clustering]] — 无监督学习的典型任务
