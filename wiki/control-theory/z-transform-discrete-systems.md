---
summary: 离散 LTI 系统的 z 变换传递函数 G(z) 的极点位置决定稳定性与动态：所有极点位于单位圆内 ⇔ 系统稳定；极点到原点的距离控制衰减率，辐角控制振荡频率。
tags: [control-theory, discrete-systems]
updated: 2026-07-06
sources:
  - raw/control-theory/2026-07-06-discrete-systems-stability-of-z-transfer-function.md
  - raw/control-theory/2026-07-06-discrete-systems-polynomial-degrees.md
---

# z 变换与离散系统

## 定义

离散时间 LTI 系统输入 $\{u_k\}$ 与输出 $\{y_k\}$ 通过 [[transfer-function]] $G(z)$ 联系，其中 $G(z)$ 是 $z$ 的有理函数。对单位冲激 $\delta_k=\{1,0,0,\dots\}$（其 z 变换为 $1$），响应恰为 $G(z)$ 的逆变换：

$$y_k = \mathcal{Z}^{-1}[G(z)]$$

因此 $G(z)$ 的极点结构完全决定系统对任意输入的行为。

## 关键点

### 极点位置 → 时域行为

将 $G(z)$ 用部分分式分解为若干简单极点之和，每种极点对应一种基本响应：

- **实极点** $\lambda$：$G(z)=\frac{1}{1-\lambda z^{-1}} \Rightarrow y_k=\lambda^k$。稳定 ⇔ $|\lambda|<1$。
- **复共轭极点** $\lambda e^{\pm j\theta}$：$y_k = 2\lambda^k \cos(\theta k)$。稳定 ⇔ $|\lambda|<1$；辐角 $\theta$ 决定振荡频率。
- **重极点** $p$（重数 $\geq 2$）：$y_k = p^k + k p^k$（因子 $k$ 来自求导），仍要求 $|p|<1$ 才稳定。

### 阻尼与振荡

- 极点到原点的**距离** = 衰减率的度量。极点越接近原点，衰减越快。
- **接近单位圆内侧**的复极点 → 轻阻尼振荡。
- **负实轴上**的实极点会产生振荡（因为 $\lambda^k$ 每步换号）。

### 稳定域

在 z 平面上，稳定域是**开单位圆盘** $|z|<1$。这与连续时间在 s 平面上"开左半平面"稳定域相对应，映射关系为 $z=e^{sT}$（[[laplace-transform]] 与 z 变换的对偶）。见 [[stability]] 中的形式判据（三条等价条件）。

## 关联概念

- [[transfer-function]] — 传递函数一般定义（连续/离散通用）
- [[stability]] — 稳定性形式判据（3 个等价条件及证明）
- [[nyquist-stability]] — 用开环频率响应判定闭环稳定性
- [[laplace-transform]] — 连续时间对应物；关系 $z=e^{sT}$
- [[generating-functions]] — z 变换即离散序列的概率生成函数（下标符号约定不同）
- [[eigendecomposition]] — 状态空间形式下，极点即状态矩阵的特征值
