---
summary: 状态空间模型 ẋ=Ax+Bu, y=Cx+Du 把系统表示为一阶向量微分方程；零输入解 x(t)=Φ(t)x₀，状态转移矩阵 Φ(t)=e^{At}，其行为由 A 的特征值控制。
tags: [control-theory, state-space]
updated: 2026-07-06
sources:
  - raw/control-theory/2026-07-06-state-space-control-state-transition-matrix.md
---

# 状态空间模型

## 定义

将 LTI 系统表示为一阶向量微分方程组：

$$\dot{\mathbf{x}}(t) = \mathbf{A}\mathbf{x}(t) + \mathbf{B}\mathbf{u}(t),\qquad \mathbf{y}(t) = \mathbf{C}\mathbf{x}(t) + \mathbf{D}\mathbf{u}(t)$$

其中 $\mathbf{x}\in\mathbb{R}^n$ 是状态向量，$\mathbf{u}$、$\mathbf{y}$ 是输入/输出。与 [[transfer-function]] 的输入-输出表示等价，但暴露了系统的**内部状态**——这是 [[kalman-filter]] 等估计器所依赖的结构。

## 关键点

### 状态转移矩阵

零输入（$\mathbf{u}=\mathbf{0}$）时 $\dot{\mathbf{x}}=A\mathbf{x}$。取 [[laplace-transform]]：

$$\mathbf{X}(s) = (s\mathbf{I}-\mathbf{A})^{-1}\mathbf{x}_0$$

逆变换给出时域解 $\mathbf{x}(t) = \Phi(t)\mathbf{x}_0$，其中**状态转移矩阵**：

$$\Phi(t) = \mathcal{L}^{-1}\{(s\mathbf{I}-\mathbf{A})^{-1}\} = \sum_{k\geq 0} \frac{\mathbf{A}^k t^k}{k!} \equiv e^{\mathbf{A}t}$$

即矩阵指数。这个恒等式来自 $(sI-A)^{-1}=\sum_k A^k s^{-(k+1)}$ 的几何级数展开。

### 谱结构与稳定性

$\Phi(t)=e^{At}$ 的行为由 $A$ 的**特征值**决定（见 [[eigendecomposition]]）：

- $A=P\Lambda P^{-1}$ 时 $e^{At}=P\,e^{\Lambda t}\,P^{-1}=P\,\text{diag}(e^{\lambda_i t})\,P^{-1}$。
- 每个 $e^{\lambda_i t}$ 是一个自由模态；$\text{Re}(\lambda_i)$ 决定衰减/发散，$\text{Im}(\lambda_i)$ 决定振荡。
- 系统渐近稳定 ⇔ 所有 $\lambda_i$ 严格位于左半 s 平面（即 [[stability]] 中的开环判据）。
- $A$ 的特征值即传递函数在 s 平面上的极点。

### 与传递函数的关系

对状态空间取 Laplace 得 $G(s) = C(sI-A)^{-1}B + D$。反之，传递函数（作为分子/分母都是多项式的有理函数）可实现为多种等价的状态空间形式（可控标准型、可观标准型、模态型等）。

## 关联概念

- [[transfer-function]] — 与输入-输出描述等价，但状态空间显式暴露内部状态
- [[laplace-transform]] — 用于求解线性状态方程
- [[eigendecomposition]] — 状态矩阵 $A$ 的谱结构 = 系统极点
- [[stability]] — 谱条件（左半平面 / 单位圆内）是稳定性判据
- [[kalman-filter]] — 建立在离散状态空间模型上的最优状态估计器
- [[linear-gaussian-model]] — Kalman 滤波器的数学基础即高斯 GLM，状态方程是其时序推广
