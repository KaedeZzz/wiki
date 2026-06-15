---
summary: 提前停止训练使权重没有时间过拟合到噪声，通过减少有效模型复杂度实现正则化。
tags: [machine-learning, regularisation, technique]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-techniques-early-stopping.md
---

# Early Stopping

## 定义

在验证损失开始上升时提前终止训练，权重未充分拟合噪声，等效于降低模型的有效复杂度。

## 关联概念

- [[regularisation]] — Early stopping 是正则化手段之一
- [[dropout]] — 另一种训练时正则化
- [[ensemble]] — 另一种降低方差的方法
