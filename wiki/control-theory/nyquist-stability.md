---
summary: Nyquist 判据用**开环**频率响应 G(e^{jθ}) 环绕 -1/K 的次数判定**闭环** KG/(1+KG) 的稳定性——闭环稳定 ⇔ 环绕数等于开环单位圆外极点数。
tags: [control-theory, stability, frequency-domain]
updated: 2026-07-06
sources:
  - raw/control-theory/2026-07-06-stability-nyquist-nyquist-stability.md
  - raw/control-theory/2026-07-06-stability-nyquist-nyquist-diagram.md
  - raw/control-theory/2026-07-06-stability-nyquist-nyquist-stability-criterion.md
  - raw/control-theory/2026-07-06-stability-nyquist-the-encirclement-property.md
  - raw/control-theory/2026-07-06-stability-nyquist-pole-arithmetics.md
  - raw/control-theory/2026-07-06-stability-nyquist-asymptote-on-nyquist-diagram.md
  - raw/control-theory/2026-07-06-stability-nyquist-nyquist-methodology.md
  - raw/control-theory/2026-07-06-stability-nyquist-proof-of-nyquist-stability-criterion.md
---

# Nyquist 稳定性

## 定义

**Nyquist 图**：将开环 [[transfer-function]] $G(z)$ 在单位圆 $z=e^{j\theta}$ 上取值，$\theta$ 从 $-\pi$ 到 $\pi$，得到复平面上的一条闭曲线（Argand 图）。因 $G$ 系数实，图关于实轴对称。

**Nyquist 稳定判据**（离散版本）：闭环 $KG/(1+KG)$ 稳定 **当且仅当** $G(e^{j\theta})$ 环绕 $-1/K$ 的次数 $\mathcal{C}$ 等于**开环极点在单位圆外的个数** $N_{op,o}$。

## 关键点

### 环绕性质（复分析事实）

对任意有理函数 $F(z)$，Nyquist 轨迹 $F(e^{j\theta})$ 绕原点的环绕次数等于**单位圆内零点数减极点数**：

$$\mathcal{C} = N_{z,i} - N_{p,i}$$

依据：对复平面上点 $c$，当 $z=e^{j\theta}$ 绕行一圈时，$\angle(e^{j\theta}-c)$ 的净增量为 $2\pi$（若 $c$ 在单位圆内或圆上）或 $0$（若在圆外）。将 $F$ 表为 $A\prod(z-z_i)/\prod(z-p_j)$ 后按辐角相加即得。

### 从 $1+KG$ 到 $-1/K$ 的平移

应用环绕性质到 $F(z)=1+KG(z)$：

- $1+KG(z)$ 的**零点** = 闭环极点，其在单位圆内个数记 $N_{cp,i}$。
- $1+KG(z)$ 的**极点** = 开环极点，其在单位圆内个数记 $N_{op,i}$。

故 $\mathcal{C}=N_{cp,i}-N_{op,i}$，其中 $\mathcal{C}$ 是 $1+KG(e^{j\theta})$ 环绕**原点**的次数。而

$$1+KG(e^{j\theta})\text{ 绕原点} \Leftrightarrow G(e^{j\theta})\text{ 绕 }-\tfrac{1}{K}$$

于是判据可就地画在 $G$ 的 Nyquist 图上，只需替换环绕对象为 $-1/K$。

### 极点算术

由 [[transfer-function]] 的多项式次数分析：$1+KG$ 分子分母同为 $\max(m,n)$ 次多项式，因此单位圆内外总极点/零点数守恒：

$$N_{cp,i}+N_{cp,o} = N_{op,i}+N_{op,o} = \max(m,n)$$

由此 $\mathcal{C}=N_{cp,i}-N_{op,i}=N_{op,o}-N_{cp,o}$。

**闭环稳定** ⇔ $N_{cp,o}=0$ ⇔ $\mathcal{C}=N_{op,o}$。这即判据的最终形式。

### 渐近线（开环极点在单位圆上时）

若 $G(z)$ 在 $z=1$ 处有极点，$G(z)=\frac{1}{z-1}F(z)$，则 Nyquist 图会趋于无穷。对 $z=e^{j\theta}\approx 1$ Taylor 展开得：

$$G(e^{j\theta}) \approx -\tfrac{1}{2}F(1)+F'(1) - j\,\tfrac{F(1)}{2\tan(\theta/2)}$$

即 $\theta\to 0$ 时轨迹渐近于**实部为常数** $-\tfrac{1}{2}F(1)+F'(1)$ 的垂直线。

### 作图方法论

1. 画 $G(z)$ 的极点-零点图。
2. 数出**开环极点在单位圆外**的个数 $\mathcal{C}=N_{op,o}$（即要求的环绕次数）。
3. 在 $\theta\in[0,\pi]$ 上画 Nyquist 轨迹。
4. 算 $G(1)$、$G(-1)$（$\theta=0, \pi$）及关键点，并标方向。
5. 利用共轭对称性补出 $\theta\in[\pi, 2\pi]$。
6. 若开环极点在单位圆上 → 画渐近线。
7. 对不同 $K$ 值确定 $-1/K$ 的位置，套用判据求闭环稳定的 $K$ 范围。

## 关联概念

- [[transfer-function]] — 定义开环 $G$ 与闭环 $KG/(1+KG)$
- [[stability]] — 稳定性一般判据；此页给出**闭环**的频域判据
- [[frequency-response]] — Nyquist 图是 $G(e^{j\theta})$ 的极坐标可视化，Bode 图给出振幅/相位分开表示
- [[z-transform-discrete-systems]] — 离散极点位置与稳定域
