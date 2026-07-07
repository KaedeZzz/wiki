---
summary: z 变换 U(z)=Σ u_k z^{-k} 是离散信号处理的核心工具——差分方程 → 代数、卷积 → 乘积、稳定 ↔ 极点在单位圆内。ROC（收敛域）决定"同一 U(z) 表达式对应哪个序列"；反变换用部分分式或长除。
tags: [communications, transforms, discrete]
updated: 2026-07-08
sources:
  - raw/communications/2026-07-08-discrete-z-transform-and-dtft-z-transform.md
  - raw/communications/2026-07-08-discrete-z-transform-and-dtft-two-sided-z-transform.md
  - raw/communications/2026-07-08-discrete-z-transform-and-dtft-region-of-convergence-of-z-transform.md
  - raw/communications/2026-07-08-discrete-z-transform-and-dtft-z-transform-of-geometric-sequence.md
  - raw/communications/2026-07-08-discrete-z-transform-and-dtft-inverse-z-transform.md
  - raw/communications/2026-07-08-discrete-z-transform-and-dtft-time-shift-properties-of-z-transform.md
  - raw/communications/2026-07-08-discrete-z-transform-and-dtft-time-shift-property-of-discrete-transforms.md
  - raw/communications/2026-07-08-discrete-z-transform-and-dtft-convolution-theorem-for-discrete-transformations.md
  - raw/communications/2026-07-08-discrete-z-transform-and-dtft-scaling-of-z-transform-with-geometric-sequence.md
  - raw/communications/2026-07-08-discrete-z-transform-and-dtft-z-transform-and-laplace-transform.md
  - raw/communications/2026-07-08-discrete-z-transform-and-dtft-z-transfer-function-of-lti-system.md
  - raw/communications/2026-07-08-discrete-z-transform-and-dtft-general-form-of-z-transfer-function.md
  - raw/communications/2026-07-08-discrete-z-transform-and-dtft-using-z-transform-to-solve-difference-equation.md
  - raw/communications/2026-07-08-discrete-z-transform-and-dtft-bode-diagram-for-discrete-systems.md
  - raw/communications/2026-07-08-discrete-z-transform-and-dtft-final-value-theorem-for-z-transform.md
  - raw/communications/2026-07-08-discrete-initial-value-theorem-for-z-transform.md
  - raw/communications/2026-07-08-discrete-z-transform-and-dtft-proof-of-final-value-theorem-for-z-transform.md
  - raw/communications/2026-07-08-discrete-z-transform-and-dtft-reverse-convolution-property-of-dtft.md
  - raw/communications/2026-07-08-discrete-z-transform-and-dtft-reverse-symmetry-property.md
  - raw/communications/2026-07-08-discrete-z-transform-and-dtft-conjugate-symmetry-property-of-dtft.md
  - raw/communications/2026-07-08-discrete-z-transform-and-dtft-dtft-inversion-formula.md
  - raw/communications/2026-07-08-discrete-z-transform-and-dtft-inverse-discrete-time-fourier-transform.md
  - raw/communications/2026-07-08-discrete-basics-formal-power-series.md
  - raw/communications/2026-07-08-discrete-basics-power-series-and-convolution.md
---

# z 变换

## 定义

对离散序列 $\{u_k\}$，**单侧 z 变换**（因果/右侧序列）：

$$U(z) = \sum_{k=0}^{\infty} u_k\,z^{-k}$$

**双侧 z 变换**：$U(z) = \sum_{k=-\infty}^{\infty} u_k\,z^{-k}$。等价于以 $D = z^{-1}$ 为变量的**形式幂级数**。z 变换是[[laplace-transform]] 的离散时间对应物（关系 $z = e^{sT}$）；见 [[z-transform-discrete-systems]] 对稳定性判据的处理。

## 关键点

### 收敛域（ROC）

严格定义包含**表达式 $U(z)$ 和收敛域**两部分：

$$\{u_k\}\ \leftrightarrow\ (U(z),\ \text{ROC})$$

**单侧 z 变换**：因果序列 → ROC 是"以某圆为边界，向外的圆环"$|z| > r$，可省略（唯一对应）。

**双侧 z 变换**：**必须给 ROC**——同一 $U(z)$ 表达式在不同 ROC 下对应不同序列（例：$\tfrac{1}{1-q z^{-1}}$ 在 $|z|>|q|$ 时是右侧 $q^k u[k]$，在 $|z|<|q|$ 时是左侧 $-q^k u[-k-1]$）。

### 几何序列（工具箱基础）

$$\mathcal{Z}\{1, q, q^2, q^3, \dots\} = \frac{1}{1 - qz^{-1}} = \frac{z}{z - q}$$

ROC：$|z| > |q|$。**任何有理 $U(z)$ 都是几何序列的线性组合**（部分分式分解）——反变换的核心。

### 性质

| 操作 | 效果 |
|---|---|
| 线性 $\alpha u + \beta v$ | $\alpha U + \beta V$ |
| 时移 $u_{k-m}$（$m>0$，因果） | $z^{-m} U(z)$ |
| 双侧时移 $u_{k-m}$ | $z^{-m} U(z)$，ROC 不变（除 $z=0, \infty$） |
| 卷积 $u * v$ | $U(z)V(z)$ |
| 几何缩放 $q^k u_k$ | $U(z/q)$（谱面缩放） |
| 差分 $u_k - u_{k-1}$ | $(1 - z^{-1})U(z)$ |
| 累积和 $\sum_{j\leq k} u_j$ | $U(z)/(1 - z^{-1})$ |
| 时反 $u_{-k}$ | $U(z^{-1})$ |
| 共轭 $\bar u_k$（实系统对称） | $\bar U(\bar z)$ |

**卷积定理**是 z 变换的核心工程价值：LTI 系统的输入-输出关系 $y = h * u$ 变成 $Y(z) = G(z)U(z)$，$G(z)$ 是[[transfer-function]]。

### 反变换

*幂级数唯一* → **任何有效方法都行**：

1. **部分分式分解**：把 $U(z)$ 拆成 $\sum \tfrac{A_i}{1 - p_i z^{-1}}$，每项对应几何序列
2. **长除**：多项式长除得到 $u_0, u_1, u_2, \dots$ 的显式头几项
3. **Taylor 展开**：将 $U(z)$ 在 $z = \infty$ 处展开成 $z^{-1}$ 幂级数
4. **围道积分**：$u_k = \tfrac{1}{2\pi j}\oint U(z) z^{k-1}\,dz$（复分析视角）
5. **逆 DTFT**：单位圆上的 z 变换 = DTFT，用逆 DTFT 公式

实际工程 99% 用部分分式。

### z 变换与 DTFT 的关系

$$U(e^{j\theta}) = U(z)\big|_{z = e^{j\theta}}$$

即 DTFT 是 z 变换在**单位圆**上的取值——见 [[fourier-transform]]。z 变换的极点/零点决定了 DTFT 幅频/相频形状（peak near pole，dip near zero）。

**共轭对称**（实系数系统）：$U(e^{-j\theta}) = \overline{U(e^{j\theta})}$——DTFT 幅频偶、相频奇。

**逆 DTFT 公式**：$u_k = \tfrac{1}{2\pi}\int_{-\pi}^{\pi} U(e^{j\theta})\,e^{jk\theta}\,d\theta$。

### 用 z 变换解差分方程

对差分方程 $y_n + a_1 y_{n-1} + \dots = b_0 u_n + \dots$，取 z 变换：

$$(1 + a_1 z^{-1} + \dots)Y(z) = (b_0 + b_1 z^{-1} + \dots)U(z) + \text{初值项}$$

代数解 $Y(z)$、部分分式分解、反 z 变换 → 时域解。这与用 Laplace 解 ODE 完全同构。

**LTI 系统的传递函数**：$G(z) = Y(z)/U(z) = \tfrac{b(z)}{a(z)}$。**离散 Bode 图**：$|G(e^{j\theta})|$ vs $\theta$，与连续 Bode 图（见 [[frequency-response]]）意义完全相同，只是频率轴变为 $[-\pi, \pi]$ 或 $[0, \pi]$。

### 初值/终值定理

$$u_0 = \lim_{z\to\infty} U(z),\qquad \lim_{n\to\infty} u_n = \lim_{z\to 1}(z-1)\,U(z)$$

终值定理要求所有极点在 $|z|<1$ 内（可能有 $z=1$ 处的孤立单极点）。这两个是**不算反变换直接得端点值**的常用工程速算。

### 一般 z-传递函数形式

$$G(z) = \frac{b_0 + b_1 z^{-1} + \dots + b_m z^{-m}}{1 + a_1 z^{-1} + \dots + a_n z^{-n}}$$

化正幂后分子分母都是 $\max(m,n)$ 次多项式，各有 $\max(m,n)$ 根（由代数基本定理）；差 $|m-n|$ 表现为原点处或无穷远的极点/零点。见 [[signals-and-lti-systems]] 中 poles/zeros 的处理。

## 关联概念

- [[laplace-transform]] — 连续时间对应物；$z = e^{sT}$
- [[fourier-transform]] — DTFT 是 z 在单位圆上的取值
- [[z-transform-discrete-systems]] — 稳定性与极点位置（控制视角）
- [[transfer-function]] — z 变换直接给出传递函数
- [[signals-and-lti-systems]] — z 变换把差分方程变代数
- [[generating-functions]] — 概率生成函数即 PMF 的 z 变换
- [[fir-and-iir-filters]] — 数字滤波器设计的核心工具
