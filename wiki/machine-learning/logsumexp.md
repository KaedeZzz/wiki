---
summary: LogSumExp 技巧通过减去最大值防止 softmax 计算中的指数溢出，确保所有 exp 输入为非正数。
tags: [machine-learning, numerical-stability, technique]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-techniques-logsumexp.md
---

# LogSumExp

## 定义

Softmax 直接计算会导致指数溢出。解决方法：
$$\text{logsoftmax}(y_k) = y_k - \text{logsumexp}(\mathbf{y})$$
$$\text{logsumexp}(\mathbf{y}) = \text{logsumexp}(\mathbf{y} - \max(\mathbf{y})) + \max(\mathbf{y})$$

减去最大值后，所有 exp 输入为非正数，结果 $\leq 1$，不会溢出。

## 关联概念

- [[loss-function]] — 交叉熵损失计算中需要数值稳定的 softmax
- [[neural-network]] — softmax 输出层的实现细节
