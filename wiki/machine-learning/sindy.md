---
summary: SINDy 从数据中发现稀疏的非线性动力学方程 $\dot{X} = \Theta(X) \Xi$，追求可解释性和简约性，而非黑箱模型。
tags: [machine-learning, scientific-computing, interpretability]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-physics-informed-ml-sparse-identification-of-nonlinear-dynamics-(sindy).md
---

# SINDy

## 定义

Sparse Identification of Nonlinear Dynamics。从数据中发现动力学方程：$\dot{X} = \Theta(X) \Xi$，其中 $\Theta(X)$ 是候选函数库，目标是在 $\Theta$ 中找到尽可能少的项来描述动力学。

## 关键点

- 动机：需要可解释且可泛化的机器学习，发现的是**方程**而非黑箱。
- 基于简约性原则（Principle of Parsimony）。
- 实现工具：PySINDy。

## 关联概念

- [[pinn]] — 另一种物理信息 ML 方法（用已知方程约束网络 vs 从数据发现方程）
