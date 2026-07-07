---
summary: 小振动方程 Mq̈+Kq=Q 通过对称广义特征值问题 (K-ω²M)u=0 得到实特征频率 ω_n 与 M-正交模态 u^(n)；用模态矩阵 U 做变换 q=Uy 把耦合系统解耦为独立单自由度振子。
tags: [physics, vibrations, eigenvalue-problem]
updated: 2026-07-06
sources:
  - raw/physics/2026-07-06-mechanics-vibrations-equation-of-motion-for-small-motion.md
  - raw/physics/2026-07-06-mechanics-vibrations-eigenvalue-problem-for-small-vibrations.md
  - raw/physics/2026-07-06-mechanics-vibrations-orthogonality-of-eigenvectors-of-eom-of-small-motion.md
  - raw/physics/2026-07-06-mechanics-vibrations-orthogonality-of-eigenmodes.md
  - raw/physics/2026-07-06-mechanics-vibrations-mass-normalisation-of-eigenvectors-of-eom-of-small-motion.md
  - raw/physics/2026-07-06-mechanics-vibrations-mass-normalisation-of-eigenmodes.md
  - raw/physics/2026-07-06-mechanics-vibrations-normal-coordinates-and-decoupling-of-eom-of-small-motion.md
  - raw/physics/2026-07-06-mechanics-vibrations-response-formula-of-vibration.md
  - raw/physics/2026-07-06-mechanics-vibrations-harmonic-free-motion-theorem.md
  - raw/physics/2026-07-06-mechanics-vibrations-buckling-with-rayleighs-quotient.md
  - raw/physics/2026-07-06-mechanics-vibrations-buckling-with-rayleighs-quotient-1.md
---

# 小振动

## 定义

对稳定平衡点附近的机械系统，[[lagrangian-mechanics]] 的二次型近似给出**小振动运动方程**：

$$\mathbf{M}\ddot{\mathbf{q}} + \mathbf{K}\mathbf{q} = \mathbf{Q}$$

- $\mathbf{q}(t) \in \mathbb{R}^N$：广义位移
- $\mathbf{M}, \mathbf{K}$：$N\times N$ **对称**质量与刚度矩阵；对稳定平衡 $\mathbf{K}$ 半正定
- $\mathbf{Q}$：外力

## 关键点

### 广义特征值问题

自由振动（$\mathbf{Q} = 0$）+ 假设 $\mathbf{q} = \mathbf{u}\,e^{i\omega t}$ → 特征方程：

$$(\mathbf{K} - \omega^2\mathbf{M})\mathbf{u} = \mathbf{0}$$

即广义特征值问题 $\mathbf{K}\mathbf{u} = \omega^2\mathbf{M}\mathbf{u}$。

**求解步骤**：

1. **特征频率**：$\det(\mathbf{K} - \omega^2\mathbf{M}) = 0$ 得 $N$ 个根 $\omega_n^2$
2. **模态形状**：对每个 $\omega_n$ 解 $\mathbf{K}\mathbf{u}^{(n)} = \omega_n^2\,\mathbf{M}\mathbf{u}^{(n)}$

**关键定理**：$\mathbf{M}, \mathbf{K}$ 对称 $\Rightarrow$ 所有 $\omega_n^2$ **实非负**、所有模态 $\mathbf{u}^{(n)}$ **$\mathbf{M}$-正交**（见下）。

**Rayleigh-Ritz** 视角：$\omega_n^2$ 是瑞利商 $\tfrac{\mathbf{u}^T\mathbf{K}\mathbf{u}}{\mathbf{u}^T\mathbf{M}\mathbf{u}}$ 的临界值——这与 [[eigendecomposition]] 里对称矩阵谱同构。

### M-正交性证明

由 $\mathbf{K}\mathbf{u}^{(n)} = \omega_n^2\mathbf{M}\mathbf{u}^{(n)}$、$\mathbf{K}\mathbf{u}^{(m)} = \omega_m^2\mathbf{M}\mathbf{u}^{(m)}$，分别左乘 $\mathbf{u}^{(m)T}$、$\mathbf{u}^{(n)T}$ 并做**对称性转置技巧**：

$$0 = (\omega_n^2 - \omega_m^2)\,\mathbf{u}^{(m)T}\mathbf{M}\mathbf{u}^{(n)}$$

$\omega_n \neq \omega_m$（无重根） $\Rightarrow \mathbf{u}^{(m)T}\mathbf{M}\mathbf{u}^{(n)} = 0$。

### 质量归一化

选择模态尺度使 $\mathbf{u}^{(n)T}\mathbf{M}\mathbf{u}^{(n)} = 1$。综合正交性：$\mathbf{U}^T\mathbf{M}\mathbf{U} = \mathbf{I}$；同时 $\mathbf{U}^T\mathbf{K}\mathbf{U} = \text{diag}(\omega_n^2)$。

### 正规坐标与解耦

设**模态矩阵** $\mathbf{U} = [\mathbf{u}^{(1)}\ \dots\ \mathbf{u}^{(N)}]$，做坐标变换 $\mathbf{q} = \mathbf{U}\mathbf{y}$。左乘 $\mathbf{U}^T$：

$$\mathbf{I}\ddot{\mathbf{y}} + \text{diag}(\omega_n^2)\,\mathbf{y} = \mathbf{U}^T\mathbf{Q}$$

**$N$ 个独立单自由度振子**。逐行为 $\ddot y_j + \omega_j^2\,y_j = f_j$，自由振动解 $y_j(t) = C_j\cos(\omega_j t + \phi_j)$，反变换：

$$\mathbf{q}(t) = \sum_j C_j\,\mathbf{u}^{(j)}\cos(\omega_j t + \phi_j)$$

即**任意小振动 = 各模态独立正弦运动的线性叠加**。这就是"谐运动定理"（沿正规坐标看是时间正弦；反变换回空间时空间形状也变正弦，因空间只是模态叠加）。

### 稳态受迫响应

若 $\mathbf{Q} = \bar{\mathbf{Q}}e^{i\omega t}$，代入并解耦得：

$$\bar{\mathbf{q}} = \mathbf{U}\left[\tfrac{1}{\text{diag}(\omega_n^2 - \omega^2)}\right]\mathbf{U}^T\bar{\mathbf{Q}}$$

若只在 $j$ 号自由度施加单一简谐力 $F_j e^{i\omega t}$：

$$H_{jk}(\omega) = \frac{q_k}{F_j} = \sum_{n=1}^N \frac{u_k^{(n)}\,u_j^{(n)}}{\omega_n^2 - \omega^2}$$

即**位移传递函数**——模态之和形式。加阻尼后即 [[vibration-transfer-functions]] 中的 receptance 函数。

### 屈曲：Rayleigh 商为负的失稳

若势能中有负贡献（如轴向压载），Rayleigh 商 $\tfrac{\mathbf{u}^T\mathbf{K}\mathbf{u}}{\mathbf{u}^T\mathbf{M}\mathbf{u}}$ 可能变为 $\leq 0$。此时对应"频率" $\omega_n^2 \leq 0$ → **纯虚频率** → 指数增长而非振荡 → **屈曲**（buckling）。Rayleigh 商成为屈曲极限载荷的估计工具。

## 关联概念

- [[eigendecomposition]] — 广义特征值问题的谱理论
- [[lagrangian-mechanics]] — 提供 $\mathbf{M}, \mathbf{K}$ 的推导
- [[vibration-transfer-functions]] — 加阻尼后的频域响应
- [[continuous-vibrations]] — $N\to\infty$ 极限，$\mathbf{M},\mathbf{K}$ 变为微分算子
- [[eigenvalue-problem-for-small-vibrations]] （见 raw 同名文件）
