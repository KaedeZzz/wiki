---
summary: Dropout 在训练时以概率 $p$（通常 ~0.2）随机将神经元置零，平滑过度拟合的行为，是一种有效的正则化技术。
tags: [machine-learning, deep-learning, regularisation]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-deep-learning-dropout.md
---

# Dropout

## 定义

训练时，对每个 mini-batch 以概率 $p$（drop out rate，通常约 0.2）随机将一层中部分神经元及其连接置零。

## 关键点

- 平滑过度特化的拟合行为，减少对特定神经元的依赖。
- 推理时不 dropout，但需按 $(1-p)$ 缩放或训练时按 $1/(1-p)$ 缩放（inverted dropout）。
- 可理解为隐式的模型 [[ensemble]]。

## 关联概念

- [[regularisation]] — Dropout 是正则化方法之一
- [[neural-network]] — Dropout 应用于神经网络训练
- [[early-stopping]] — 另一种正则化手段
