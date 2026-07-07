---
summary: 拉格朗日力学用 L=T-V 与 Euler-Lagrange 方程 d/dt(∂L/∂q̇)-∂L/∂q=Q 把动力学统一表达在广义坐标 q 上；小振动近似下 T=½q̇ᵀMq̇, V=½qᵀKq，得到 Mq̈+Kq=Q 的矩阵形式。
tags: [physics, mechanics, lagrangian]
updated: 2026-07-06
sources:
  - raw/physics/2026-07-06-mechanics-langrangian-lagrangian.md
  - raw/physics/2026-07-06-mechanics-langrangian-lagrangian-mechanics.md
  - raw/physics/2026-07-06-mechanics-langrangian-lagranges-equation.md
  - raw/physics/2026-07-06-mechanics-langrangian-lagranges-equation-for-dynamical-systems.md
  - raw/physics/2026-07-06-mechanics-langrangian-lagrange-for-small-motions.md
---

# 拉格朗日力学

## 定义

**拉格朗日量**：

$$\mathcal{L} = T - V$$

其中 $T$ 为动能、$V$ 为势能。**Euler-Lagrange 方程**给出保守系统的运动方程：

$$\frac{d}{dt}\frac{\partial\mathcal{L}}{\partial \dot q_j} - \frac{\partial\mathcal{L}}{\partial q_j} = 0$$

**广义坐标** $q_j$ 是选择系统状态的任意坐标，无需笛卡尔；约束通过坐标选择自动满足。

## 关键点

### 与 Newton 力学的等价性

$\mathcal{L}$ 表述 = Newton 表述 + Lagrange 乘子处理约束。**优势**：

- **坐标无关**：换到极坐标、旋转坐标、约束坐标只是换 $q_j$，方程形式不变
- **保守/耗散/受迫**统一：外力/摩擦用广义力 $Q_j$ 加到方程右端
- **变分原理**：Euler-Lagrange 等价于**最小作用量** $\delta\int\mathcal{L}\,dt = 0$——这是量子力学（路径积分）和场论的起点

**受迫系统**（有非保守外力 $Q_j$）：

$$\frac{d}{dt}\frac{\partial T}{\partial \dot q_j} - \frac{\partial T}{\partial q_j} + \frac{\partial V}{\partial q_j} = Q_j$$

### 小振动近似（quadratic Lagrangian）

在稳定平衡 $\mathbf{q}=\mathbf{0}$ 附近做 Taylor 展开：

- $V(\mathbf{q}) = V_0 + \sum \tfrac{\partial V}{\partial q_j}q_j + \tfrac{1}{2}\sum \tfrac{\partial^2 V}{\partial q_j \partial q_k}q_j q_k + \dots$
- 平衡点：$\tfrac{\partial V}{\partial q_j}\big|_{eq} = 0$
- 忽略 $V_0$ 与 3 阶以上项

结果 $V$ 简化为**二次型**：

$$V = \tfrac{1}{2}\,\mathbf{q}^T\mathbf{K}\mathbf{q},\quad \mathbf{K} = \left[\tfrac{\partial^2 V}{\partial q_j \partial q_k}\right]_{eq}\ (\text{对称，刚度矩阵})$$

类似地 $T$（在平衡处评估 $\mathbf{M}$）：

$$T = \tfrac{1}{2}\,\dot{\mathbf{q}}^T\mathbf{M}\dot{\mathbf{q}}$$

代回 Euler-Lagrange 得到**线性小振动方程**：

$$\mathbf{M}\ddot{\mathbf{q}} + \mathbf{K}\mathbf{q} = \mathbf{Q}$$

$N$ 个耦合二阶 ODE。这套推导为整个 [[small-vibrations]] 与 [[vibration-transfer-functions]] 的分析铺路。

### 从 $\mathcal{L}$ 推向 Hamiltonian 与状态空间

引入广义动量 $p_j = \partial\mathcal{L}/\partial\dot q_j$，做 Legendre 变换得 Hamiltonian $H(q,p) = \sum p_j\dot q_j - \mathcal{L}$。Hamilton 方程 $\dot q = \partial H/\partial p,\ \dot p = -\partial H/\partial q$ 是**状态空间**动力学系统的自然结构——见 [[state-space-model]] 与 [[dynamical-systems]]。

## 关联概念

- [[small-vibrations]] — 拉格朗日小振动 → 矩阵特征值问题
- [[rigid-body-dynamics]] — 拉格朗日等价于 Newton，但坐标自由
- [[state-space-model]] — Hamilton 视角就是状态空间
- [[noether-and-parsimony]] — Noether 定理：$\mathcal{L}$ 的每个连续对称给一个守恒量
