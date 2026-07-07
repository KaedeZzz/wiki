---
summary: 动力系统由状态 x、输入 u、输出 y 组成，需满足 (i) 未来状态由当前状态与输入完全决定 (ii) 输出是当前状态与输入的无记忆函数；状态空间形式 ẋ=f(x,u), y=g(x,u) 可在平衡点线性化为 δẋ=Aδx+Bδu，Laplace 解 X(s)=(sI-A)⁻¹x₀+(sI-A)⁻¹BU(s) 给出传递函数矩阵 G(s)=D+C(sI-A)⁻¹B。
tags: [physics, dynamical-systems, state-space]
updated: 2026-07-06
sources:
  - raw/physics/2026-07-06-mechanics-dynamical-systems-dynamical-system.md
  - raw/physics/2026-07-06-mechanics-dynamical-systems-implicit-state-equation.md
  - raw/physics/2026-07-06-mechanics-dynamical-systems-linearisation-of-state-space-dynamical-system-model.md
  - raw/physics/2026-07-06-mechanics-dynamical-systems-linearisation-of-implicit-state-equations.md
  - raw/physics/2026-07-06-mechanics-dynamical-systems-laplace-solution-of-linear-state-equations.md
  - raw/physics/2026-07-06-mechanics-dynamical-systems-koopman-operator-theory-dynamical-system-as-differential-equation.md
  - raw/physics/2026-07-06-mechanics-dynamical-systems-koopman-operator-theory-discrete-time-dynamical-system.md
  - raw/physics/2026-07-06-mechanics-dynamical-systems-koopman-operator-theory-linear-dynamics.md
  - raw/physics/2026-07-06-mechanics-dynamical-systems-koopman-operator-theory-flow-map.md
  - raw/physics/2026-07-06-mechanics-dynamical-systems-koopman-operator-theory-eigen-decomposition.md
---

# 动力系统

## 定义

**动力系统**：具有记忆的系统——输出 $\mathbf{y}(t_1)$ 不仅依赖当前输入 $\mathbf{u}(t_1)$，也依赖过往输入 $\mathbf{u}(t)|_{t<t_1}$。**状态** $\mathbf{x}(t) \in \mathbb{R}^n$ 是描述这个记忆所需的最小变量集，满足两个性质：

1. **状态转移性**：对任意 $t_0 < t_1$，$\mathbf{x}(t_1)$ 由 $\mathbf{x}(t_0)$ 与 $\{\mathbf{u}(t) : t_0 \leq t \leq t_1\}$ 完全确定
2. **输出无记忆性**：$\mathbf{y}(t_1)$ 是 $\mathbf{x}(t_1)$ 与 $\mathbf{u}(t_1)$ 的无记忆函数

即"$\mathbf{x}(t_0)$ 完整概括了 $t_0$ 之前一切输入和状态的影响"。三元变量：

$$\mathbf{u}(t) \in \mathbb{R}^m \text{（输入）},\quad \mathbf{x}(t) \in \mathbb{R}^n \text{（状态）},\quad \mathbf{y}(t) \in \mathbb{R}^p \text{（输出）}$$

## 关键点

### 三种表述形式

**连续时间显式（微分方程形式）**：

$$\dot{\mathbf{x}}(t) = \vec{f}(\mathbf{x}, \mathbf{u}, t),\qquad \mathbf{y}(t) = \vec{g}(\mathbf{x}, \mathbf{u}, t)$$

**连续时间隐式**：

$$\vec{F}(\dot{\mathbf{x}}, \mathbf{x}, \mathbf{u}) = \mathbf{0}$$

**离散时间**（[[koopman-and-dmd]] 里 Koopman 的天然形式）：

$$\mathbf{x}_{k+1} = F(\mathbf{x}_k) \qquad \text{（}F\text{ 称为 map）}$$

**流映射**（flow map）：把当前状态推进到 $t$ 秒后

$$F_t(\mathbf{x}(t_0)) = \mathbf{x}(t_0) + \int_{t_0}^{t_0+t} \vec{f}(\mathbf{x}(\tau))\,d\tau$$

### 平衡点线性化

**平衡** $(\mathbf{x}_e, \mathbf{u}_e)$：$\vec{f}(\mathbf{x}_e, \mathbf{u}_e) = \mathbf{0}$。对小扰动 $\mathbf{x} = \mathbf{x}_e + \delta\mathbf{x}$、$\mathbf{u} = \mathbf{u}_e + \delta\mathbf{u}$ 做 Taylor 展开：

$$\dot{\delta\mathbf{x}} \approx \mathbf{A}\,\delta\mathbf{x} + \mathbf{B}\,\delta\mathbf{u},\qquad \delta\mathbf{y} \approx \mathbf{C}\,\delta\mathbf{x} + \mathbf{D}\,\delta\mathbf{u}$$

其中

$$\mathbf{A} = \tfrac{\partial\vec f}{\partial\mathbf{x}}\bigg|_{eq},\quad \mathbf{B} = \tfrac{\partial\vec f}{\partial\mathbf{u}}\bigg|_{eq},\quad \mathbf{C} = \tfrac{\partial\vec g}{\partial\mathbf{x}}\bigg|_{eq},\quad \mathbf{D} = \tfrac{\partial\vec g}{\partial\mathbf{u}}\bigg|_{eq}$$

**Jacobi 矩阵**（见 [[calculus]]）。对隐式系统 $\vec F(\dot{\mathbf{x}},\mathbf{x},\mathbf{u})=0$，线性化给 $\mathbf{L}\dot{\delta\mathbf{x}} + \mathbf{M}\delta\mathbf{x} + \mathbf{N}\delta\mathbf{u} = \mathbf{0}$，若 $\mathbf{L}$ 可逆则可解为显式形式 $\dot{\delta\mathbf{x}} = -\mathbf{L}^{-1}\mathbf{M}\delta\mathbf{x} - \mathbf{L}^{-1}\mathbf{N}\delta\mathbf{u}$。

### 线性系统的谱分析

对 $\dot{\mathbf{x}} = \mathbf{A}\mathbf{x}$，解为 $\mathbf{x}(t) = e^{\mathbf{A}t}\mathbf{x}_0$。谱分解 $\mathbf{A} = T\Lambda T^{-1}$（[[eigendecomposition]]）：

$$\mathbf{x}(t) = T\,e^{\Lambda t}\,T^{-1}\mathbf{x}_0$$

**内在坐标** $\mathbf{z} = T^{-1}\mathbf{x}$ 里，动力学**解耦**：

$$\dot{\mathbf{z}} = \Lambda \mathbf{z} \quad \Longleftrightarrow \quad \dot z_i = \lambda_i z_i$$

每个特征值 $\lambda_i$ 是一个独立模态：$\text{Re}(\lambda_i)$ 决定衰减/发散，$\text{Im}(\lambda_i)$ 决定振荡频率。稳定 ⇔ 所有 $\lambda_i$ 在开左半平面（连续时间）或单位圆内（离散时间）——见 [[stability]]。

### Laplace 解与传递函数矩阵

对线性 $\dot{\mathbf{x}} = \mathbf{A}\mathbf{x} + \mathbf{B}\mathbf{u}$、$\mathbf{y} = \mathbf{C}\mathbf{x} + \mathbf{D}\mathbf{u}$，取 [[laplace-transform]]：

$$\mathbf{X}(s) = (s\mathbf{I} - \mathbf{A})^{-1}\mathbf{x}_0 + (s\mathbf{I} - \mathbf{A})^{-1}\mathbf{B}\mathbf{U}(s)$$

**响应 = 初态响应 + 输入响应**。$s\mathbf{I} - \mathbf{A}$ 奇异 ⇔ $s$ 是 $\mathbf{A}$ 的特征值 = 系统极点。

**传递函数矩阵**（零初值 $\mathbf{x}_0 = \mathbf{0}$）：

$$\mathbf{G}(s) = \mathbf{D} + \mathbf{C}(s\mathbf{I} - \mathbf{A})^{-1}\mathbf{B}$$

条目 $(i,j)$ 是从输入 $u_j$ 到输出 $y_i$ 的[[transfer-function]]。这是**多变量控制**的基石。

## 关联概念

- [[state-space-model]] — 控制论中的等价概念（一个更工程化的入口）
- [[eigendecomposition]] — $\mathbf{A}$ 的谱分析
- [[laplace-transform]] — 求解线性方程的核心工具
- [[stability]] — $\mathbf{A}$ 的特征值判据
- [[transfer-function]] — Laplace 域中的输入-输出关系
- [[kalman-filter]] — 状态空间上的贝叶斯滤波
- [[koopman-and-dmd]] — 用**观测函数**上的线性化替代状态的线性化
- [[calculus]] — Jacobi 是线性化的核心
