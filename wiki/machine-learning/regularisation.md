---
summary: 正则化是通过在损失函数中加入额外项来缩小泛化差距的方法，本质上是对参数施加先验偏好。L2 正则化是最常见的形式。
tags: [machine-learning, basics]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-basics-theories-regularisation.md
  - raw/machine-learning/2026-06-08-basics-theories-l2-regularisation.md
---

# 正则化

## 定义

正则化是减小泛化差距的方法集合，技术上意味着在损失函数中加入额外项：
$$\theta^* = \arg\min_\theta \left[\sum_i L(f(\hat{x}_i; \theta), y_i) - \log p(\theta)\right]$$
其中 $p(\theta)$ 是先验，表达对某些参数的偏好。

## 关键点

- **L2 正则化**：$\theta^* = \arg\min_\theta \left[\sum_i L(f(\hat{x}_i; \theta), \hat{y}_i) + \gamma \|\theta\|^2\right]$，鼓励参数接近零。
- 正则化本质上是贝叶斯视角下的参数先验。
- 其他正则化手段包括 [[dropout]]、[[early-stopping]]、[[ensemble]]。

## 关联概念

- [[loss-function]] — 正则化修改的对象
- [[dropout]] — 通过随机丢弃神经元实现正则化
- [[early-stopping]] — 提前停止训练防止过拟合
- [[ensemble]] — 通过多模型平均降低方差
