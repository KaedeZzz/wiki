---
summary: 阻尼小振动的频响 H_jk(ω) = Σ u^(n)_j u^(n)_k / (ω_n² + 2iζ_n ω_n ω - ω²) 有三种"口味"（receptance/mobility/inertance，差 iω 因子）；峰宽 Δω≈2ζ_n ω_n；模态重叠因子决定该用模态分析还是统计能量法。
tags: [physics, vibrations, frequency-domain]
updated: 2026-07-06
sources:
  - raw/physics/2026-07-06-mechanics-vibrations-transfer-function-of-vibration.md
  - raw/physics/2026-07-06-mechanics-vibrations-receptance-function.md
  - raw/physics/2026-07-06-mechanics-vibrations-mobility-function.md
  - raw/physics/2026-07-06-mechanics-vibrations-inertance-function.md
  - raw/physics/2026-07-06-mechanics-vibrations-discrete-transfer-function-with-modal-damping.md
  - raw/physics/2026-07-06-mechanics-vibrations-half-power-bandwidth-of-receptance-function.md
  - raw/physics/2026-07-06-mechanics-vibrations-modal-overlap.md
  - raw/physics/2026-07-06-mechanics-vibrations-reciprocity-theorem.md
  - raw/physics/2026-07-06-mechanics-vibrations-polar-plots.md
  - raw/physics/2026-07-06-mechanics-vibrations-bode-diagram-of-response-formula-of-vibration.md
  - raw/physics/2026-07-06-mechanics-vibrations-bode-diagram-of-response-formula-of-vibration-1.md
  - raw/physics/2026-07-06-mechanics-vibrations-transient-response-for-arbitrary-loads.md
  - raw/physics/2026-07-06-mechanics-vibrations-finding-impulse-response-from-vibration-transfer-function.md
  - raw/physics/2026-07-06-mechanics-vibrations-properties-of-frequency-response-curves-of-vibration-transfer-function.md
---

# 振动传递函数

## 定义

在 $j$ 号自由度施加正弦力 $F_j e^{i\omega t}$，$k$ 号自由度的响应记为 $q_k = H_{jk}(\omega)\,F_j e^{i\omega t}$。**$H_{jk}(\omega)$ 是从激励点 $j$ 到测量点 $k$ 的传递函数**（frequency response function, FRF）。含黏性阻尼时：

$$H_{jk}(\omega) = \sum_{n=1}^N \frac{u_k^{(n)}\,u_j^{(n)}}{\omega_n^2 + 2i\zeta_n\omega_n\omega - \omega^2}$$

其中 $\zeta_n$ 是第 $n$ 阶模态的**阻尼比**。

## 关键点

### 三种"口味"：位移/速度/加速度

对同一激励取三种响应量：

| 名称 | 响应 | 表达式 |
|---|---|---|
| **Receptance** $H_q$ | 位移 | $\frac{1}{1 - \omega^2/\omega_n^2 + 2i\zeta_n\omega/\omega_n}$（单模态归一化） |
| **Mobility** $H_v$ | 速度 | $(i\omega/\omega_n)\cdot H_q$ |
| **Inertance** $H_a$ | 加速度 | $(i\omega/\omega_n)^2\cdot H_q$ |

三者只差 $i\omega$ 因子，本质是**同一物理系统**的三种视角。工程实践中根据传感器类型（LVDT/加速度计等）取其一。

### 频响的 3 段渐近

以 receptance 为例，log magnitude 与相位随 $\omega/\omega_n$ 变化：

| $\omega/\omega_n$ | $|H|_{\text{dB}}$ | 相位 $\phi$ |
|---|---|---|
| $\to 0$（低频） | $0$ | $0$ |
| $= 1$（共振） | $20\log(1/(2\zeta_n))$ | $-\pi/2$ |
| $\to \infty$（高频） | $-40\log(\omega/\omega_n)$ | $-\pi$ |

**共振峰高度 $1/(2\zeta_n)$** 直接给出阻尼——阻尼越小，峰越尖越高。

### 半功率带宽

共振峰的 $-3$ dB 宽度（半功率点）：

$$\Delta\omega \approx 2\zeta_n\omega_n \quad(\zeta_n \ll 1)$$

对 receptance、mobility、inertance 三者都近似成立。用测得带宽反算 $\zeta_n$ 是**实验模态分析**的常规手段。

### 模态重叠因子

系统有多阶模态时，定义：

$$\beta = \frac{\Delta\omega}{\omega_{n+1} - \omega_n}$$

- **$\beta \ll 1$**（低重叠）：模态峰分得开——每个共振区行为=单自由度；两峰之间响应≈两侧模态贡献之和
- **$\beta \gg 1$**（高重叠）：任一频率下多模态叠加——转向**统计能量法**（SEA）等统计方法

**低频**通常低重叠（可做模态分析）；**高频**（结构声学、宽带激励）通常高重叠。

### 互易定理

$$H_{jk}(\omega) = H_{kj}(\omega)$$

激励点和观测点**互换给出相同的传递函数**——直接从公式 $\tfrac{u_k^{(n)}u_j^{(n)}}{\dots}$ 关于 $j,k$ 对称即得。物理直觉：机械阻抗矩阵对称（能量守恒 + 线性）。工程含义：可以选择方便的位置激励，然后到远端测量。

### 极坐标图

Mobility 的极坐标图（复平面轨迹）：

$$H_v = \frac{ip/(1-p^2 + 2i\zeta p)},\quad p = \omega/\omega_n$$

代数化简后，实虚部满足圆方程 $U^2 + V^2 = (1/(4\zeta))^2$——**mobility 极坐标是圆**（对任意 $\zeta$）。Receptance 与 inertance 在 $\zeta\ll 1$ 时近似为圆。共振时 mobility 极径最大 $1/(2\zeta)$。

**用途**：实验数据在极坐标上圆度是快速判断该频段是单模态主导还是多模态混合的可视工具。

### 瞬态与任意力响应

对任意时变力 $f(t)$，输出为**卷积**（时域）或**乘积**（频域）：

$$y(t) = g(t) * f(t) \Longleftrightarrow Y(\omega) = G(\omega)\,F(\omega)$$

冲激响应可由 $H_{jk}$ 反 Laplace 得到（[[laplace-transform]]）：

$$g_{jk}(t) = \sum_n \frac{u_j^{(n)}u_k^{(n)}}{\omega_n}\,e^{-\zeta_n\omega_n t}\sin(\omega_n t)$$

即**每个模态是一个衰减正弦**，工程上用来做时域仿真、机械噪声分析、结构监测中的故障诊断。

## 关联概念

- [[small-vibrations]] — 提供无阻尼模态和特征频率
- [[laplace-transform]] — 传递函数背后的复频域机制
- [[frequency-response]] — 控制论中的通用频响概念，本页是其力学特化
- [[stability]] — 无阻尼系统极点在虚轴（边缘稳定）；阻尼把极点推入左半平面
- [[transfer-function]] — 通用传递函数概念
