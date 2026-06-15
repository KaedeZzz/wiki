---
summary: PINN 用神经网络直接表示 PDE 的未知解，通过最小化初始条件、边界条件和 PDE 残差的复合损失求解，无需网格离散化。也可用于反问题中同时估计状态和参数。
tags: [machine-learning, deep-learning, scientific-computing]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-deep-learning-physics-informed-neural-network-(pinn).md
  - raw/machine-learning/2026-06-08-deep-learning-autoencoders-solving-burger's-equation-with-koopman-operator-theory.md
---

# 物理信息神经网络（PINN）

## 定义

用神经网络 $u_\theta(x, t)$ 直接逼近 PDE 的未知解，而非在网格点上离散求解。

## 关键点

**正问题**：
1. 表示解：$u(x, t) \approx u_\theta(x, t)$
2. 定义 PDE 残差：$R_\theta(x, t) = \partial_t u_\theta + Q[u_\theta]$
3. 最小化复合损失：$L(\theta) = L_{ic} + L_{bc} + L_r$（初始条件 + 边界条件 + 内部配点残差）
4. 得到无网格解：$\theta^* = \arg\min_\theta L(\theta)$

**反问题**：PDE 结构已知但参数 $\lambda$ 未知，同时估计状态 $u$ 和参数 $\lambda$：
$$L(\theta, \lambda) = L_d + L_f(\theta, \lambda) + L_{\text{physics}}$$

**Koopman 算子方法**：用自编码器将 Burgers 方程通过 Cole-Hopf 变换转为热方程，在傅里叶空间对角化求解。

## 关联概念

- [[neural-network]] — PINN 的函数逼近器
- [[loss-function]] — PINN 的复合损失设计
- [[sindy]] — 另一种物理信息 ML 方法，发现可解释方程
