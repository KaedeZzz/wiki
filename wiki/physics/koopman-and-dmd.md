---
summary: Koopman 算子 K g = g∘F 把非线性动力系统"抬升"到观测函数空间上变成线性——代价是无穷维；其特征函数 ψ 提供内在坐标使动力学解耦。DMD (Schmid 2010) 从数据 X_{k+1}≈AX_k 得到有限维 Koopman 近似；Lusch 等用深度学习寻找 Koopman 不变子空间。
tags: [physics, dynamical-systems, koopman, dmd]
updated: 2026-07-06
sources:
  - raw/physics/2026-07-06-mechanics-dynamical-systems-koopman-operator-theory-koopman-operator.md
  - raw/physics/2026-07-06-mechanics-dynamical-systems-koopman-operator-theory-linearity-of-koopman-operator.md
  - raw/physics/2026-07-06-mechanics-dynamical-systems-koopman-operator-theory-koopman-eigenfunction.md
  - raw/physics/2026-07-06-mechanics-dynamical-systems-koopman-operator-theory-eigenvalue-lattice.md
  - raw/physics/2026-07-06-mechanics-dynamical-systems-koopman-operator-theory-koopman-invariant-subspace.md
  - raw/physics/2026-07-06-mechanics-dynamical-systems-koopman-operator-theory-intrinsic-coordinates-of-koopman-invariant-subspace.md
  - raw/physics/2026-07-06-mechanics-dynamical-systems-koopman-operator-theory-koopman-mode-decomposition.md
  - raw/physics/2026-07-06-mechanics-dynamical-systems-dynamic-mode-decomposition.md
---

# Koopman 算子与 DMD

## 定义

**核心洞察**：非线性动力系统 $x_{k+1} = F(x_k)$ 在**状态空间**中是非线性的，但在**观测函数空间** $\mathcal{F}$ 上诱导的**Koopman 算子** $\mathcal{K}$ 是**线性**的：

$$(\mathcal{K}\,g)(x) = g(F(x)) = g \circ F$$

代价：$\mathcal{K}$ 作用在无穷维函数空间上。**动态模态分解（DMD）**是它的**有限维数据驱动近似**。

## 关键点

### Koopman 算子的线性性

对任意观测 $g_1, g_2$ 与标量 $\alpha_1, \alpha_2$：

$$\mathcal{K}_t(\alpha_1 g_1 + \alpha_2 g_2) = \alpha_1(g_1 \circ F_t) + \alpha_2(g_2 \circ F_t) = \alpha_1 \mathcal{K}_t g_1 + \alpha_2 \mathcal{K}_t g_2$$

**这条线性性对底层动力 $F$ 是否非线性无关**。这是全部 Koopman 理论的立足点。

**连续时间版本**：$\mathcal{K}$ 是一族变换 $\{\mathcal{K}_t\}$ 的**无穷小生成元**：

$$\mathcal{K}\,g = \lim_{t\to 0}\frac{\mathcal{K}_t g - g}{t} = \lim_{t\to 0}\frac{g\circ F_t - g}{t}$$

### Koopman 特征函数与特征值

$$\psi(x_{k+1}) = \mathcal{K}_{\Delta t}\,\psi(x_k) = \lambda\,\psi(x_k)$$

在特征函数 $\psi$ 上看，动力学是**纯几何**放大 $\lambda$。连续时间用链式法则得：

$$\nabla\psi(x)\cdot f(x) = \lambda\,\psi(x)$$

**非线性 PDE**——虽形式简洁但一般难解。近似路线：

- 数据驱动回归（DMD 及其扩展）
- 解 Laurent 级数
- 深度学习拟合（Lusch et al. 2018；见 [[reading-list]]）

**连续 vs 离散特征值**：$\lambda_{\text{cont}} \leftrightarrow e^{\lambda_{\text{cont}}\,\Delta t}$（与 z 平面到 s 平面的映射一致，见 [[z-transform-discrete-systems]]）。

### 特征值格 & Noether 联系

Koopman 谱有**乘法结构**：$\mathcal{K}(\psi_1\psi_2) = \lambda_1\lambda_2\,\psi_1\psi_2$——两个特征函数的积仍是特征函数。因此**少数生成特征函数**可以由乘法生成整个谱格。

**Noether 类推**：见 [[noether-and-parsimony]]。经典 Noether 定理"每个连续对称给一个守恒量"在 Koopman 视角下：**每个对称给一个 $\lambda=0$ 的特征函数**（守恒量沿轨道不变，即 $\mathcal{K}\psi = \psi$）。

### 不变子空间与内在坐标

**Koopman 不变子空间**：$\text{span}\{g_1,\dots,g_p\}$ 使得

$$\mathcal{K}\,g_i = \sum_j M_{ij}\,g_j$$

即算子在这些函数上作用后仍留在同一子空间中。此时 $\mathcal{K}$ 在这个 $p$-维子空间上有**有限维矩阵表示 $\mathbf{M}$**——正是从无穷维回到可算的关键。

**内在坐标**：$\mathbf{M}$ 的**左特征向量** $\boldsymbol{\xi}_\alpha$（$\boldsymbol{\xi}_\alpha \mathbf{M} = \alpha\,\boldsymbol{\xi}_\alpha$）给出

$$\psi_\alpha(x) = \boldsymbol{\xi}_\alpha \cdot \mathbf{y}(x)$$

即用观测向量 $\mathbf{y}(x) = (g_1(x),\dots,g_p(x))^T$ 构造特征函数。**在这些坐标下动力学变线性**——这就是深度 Koopman 网络所要学的目标。

### Koopman 模态分解

对**向量值观测** $\mathbf{g}(x) = (g_1(x),\dots,g_p(x))^T$，用特征函数基（在保守系统中正交）展开：

$$\mathbf{g}(x) = \sum_{j=1}^{\infty} \psi_j(x)\,\mathbf{v}_j$$

其中 $\mathbf{v}_j$ 是**Koopman 模态**（观测空间中的方向），由投影 $\mathbf{v}_j = (\langle\psi_j, g_1\rangle,\dots,\langle\psi_j, g_p\rangle)^T$ 给出。

**时间演化**：

$$\mathbf{g}(x_k) = \mathcal{K}^k\,\mathbf{g}(x_0) = \sum_{j} \lambda_j^k\,\psi_j(x_0)\,\mathbf{v}_j$$

三元组 $\{(\lambda_j, \psi_j, \mathbf{v}_j)\}$ 就是 **Koopman 模态分解**——每个 $j$ 是一个时间上按 $\lambda_j^k$ 演化、空间上是 $\mathbf{v}_j$ 分布的相干模式。

### 动态模态分解（DMD）

**Schmid 2010 的原始 DMD**：从数据快照矩阵 $\mathbf{X} = [\mathbf{x}_0,\dots,\mathbf{x}_{k-1}]$、$\mathbf{X}' = [\mathbf{x}_1,\dots,\mathbf{x}_k]$，找线性算子 $\mathbf{A}$ 使 $\mathbf{X}' \approx \mathbf{A}\mathbf{X}$：

$$\mathbf{A} = \mathbf{X}'\mathbf{X}^{+} \quad(\mathbf{X}^+ = \text{SVD 伪逆，见 [[matrix-decomposition]]})$$

$\mathbf{A}$ 的特征值 = 数据中的**时频模式**；特征向量 = **空间模态**。**DMD 是把状态观测本身作为观测函数** $g(x) = x$ 时的 Koopman 近似——最简单一层。

**扩展**：Extended DMD 用非线性字典 $\{\phi_1(x),\phi_2(x),\dots\}$ 作为观测，直接近似 Koopman 在更大子空间上；深度 Koopman（Lusch 等）用神经网络学 $\phi$。

### 用途

- **流体动力学**：从实验 PIV 数据抽取相干模式（Schmid 的原始动机）
- **降阶模型**：把非线性 CFD/CFD-DEM 压到几十个模态
- **控制**：非线性系统在 Koopman 坐标下变线性，可套 LQR / MPC
- **状态估计**：结合 Kalman 滤波（[[kalman-filter]]）
- **机器学习基础**：SINDy、[[sindy]] 与 Koopman 是**数据驱动动力系统**双子

## 关联概念

- [[dynamical-systems]] — 传统状态空间视角
- [[eigendecomposition]] — 谱是 Koopman/DMD 的核心
- [[matrix-decomposition]] — SVD 是 DMD 求 $\mathbf{A}$ 的骨干
- [[laplace-transform]] — 连续/离散谱转换 $z = e^{s\Delta t}$
- [[sindy]] — 数据驱动动力学系的另一路线（稀疏回归）
- [[autoencoder]] — 深度 Koopman 用 autoencoder 学习特征函数
- [[noether-and-parsimony]] — 对称 ↔ Koopman $\lambda=0$ 特征函数
- [[reading-list]] — Schmid 2010、Rowley 2009、Lusch 2018、Gin 2020
