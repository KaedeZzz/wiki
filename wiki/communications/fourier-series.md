---
summary: 周期信号可展成正弦/复指数的加权和：g(t)=Σ c_n e^{jnω₀t}，系数 c_n = (1/T)∫g(t)e^{-jnω₀t}dt；Parseval 定理 Σ|c_n|² = 时域平均功率把频域几何联系到能量。
tags: [communications, fourier, frequency-domain]
updated: 2026-07-08
sources:
  - raw/communications/2026-07-08-continuous-fourier-series-fourier-series.md
  - raw/communications/2026-07-08-continuous-fourier-series-complex-fourier-series.md
  - raw/communications/2026-07-08-continuous-fourier-series-fourier-series-coefficients.md
  - raw/communications/2026-07-08-continuous-fourier-series-convolution-property-of-fourier-series.md
  - raw/communications/2026-07-08-continuous-fourier-series-fourier-series-transformations.md
  - raw/communications/2026-07-08-continuous-basics-parsevals-theorem.md
  - raw/communications/2026-07-08-continuous-basics-integral-of-periodic-spectrum.md
---

# Fourier 级数

## 定义

任何在 $[-\pi, \pi]$ 上周期的函数 $g(t)$ 有**实 Fourier 级数**：

$$g(t) = \frac{a_0}{2} + \sum_{n=1}^{\infty}\{a_n\cos(nt) + b_n\sin(nt)\}$$

$$a_n = \frac{1}{\pi}\int_{-\pi}^{\pi} g(t)\cos(nt)\,dt,\quad b_n = \frac{1}{\pi}\int_{-\pi}^{\pi} g(t)\sin(nt)\,dt$$

**复 Fourier 级数**（更紧凑）：

$$g(t) = \sum_{n=-\infty}^{\infty} c_n\,e^{jnt},\quad c_n = \frac{1}{2\pi}\int_{-\pi}^{\pi} g(t)\,e^{-jnt}\,dt$$

## 关键点

### 任意周期 $T$

周期 $T \neq 2\pi$：用"时间轴伸缩因子 $T/(2\pi)$"，得**基频** $\omega_0 = 2\pi/T$：

$$g(t) = \sum_{n=-\infty}^{\infty} c_n\,e^{jn\omega_0 t},\quad c_n = \frac{1}{T}\int_{\alpha}^{\alpha+T} g(t)\,e^{-jn\omega_0 t}\,dt$$

### 三种系数的关系

$$c_0 = \frac{a_0}{2},\quad c_n = \frac{a_n - jb_n}{2}\ (n>0),\quad c_{-n} = \bar{c}_n\ (\text{实信号})$$

**实信号 ⇔ 系数共轭对称** $c_{-n} = \bar{c}_n$——这条对称性在 [[fourier-transform]] 和 DFT 里同样成立。

### 卷积性质

两个周期信号 $g_1, g_2$ 的**周期卷积**：$(g_1 \star g_2)(t) = \int_0^T g_1(\tau)g_2(t-\tau)\,d\tau$。相应的 Fourier 系数：

$$(g_1 \star g_2) \leftrightarrow T \cdot c_n^{(1)} c_n^{(2)}$$

时域卷积 → 频域乘积，反之亦然。这是把 LTI 卷积在频域简化为标量乘法的核心工具（应用于 [[discrete-fourier-transform-and-fft]] 里的快速卷积）。

### 常用变换

| 时域操作 | 频域效果 |
|---|---|
| 时移 $g(t-t_0)$ | $c_n e^{-jn\omega_0 t_0}$ |
| 频移 $g(t)e^{jn_0\omega_0 t}$ | $c_{n-n_0}$（系数序号平移） |
| 微分 $\dot g(t)$ | $jn\omega_0 c_n$ |
| 积分 $\int g$ | $c_n/(jn\omega_0)$（$n\neq 0$） |
| 共轭 $\bar g(t)$ | $\bar c_{-n}$ |
| 时间反演 $g(-t)$ | $c_{-n}$ |

### Parseval 定理

**时域平均功率 = 频域系数模平方和**：

$$\frac{1}{T}\int_0^T |g(t)|^2\,dt = \sum_{n=-\infty}^{\infty} |c_n|^2$$

物理含义：功率**均匀分布**在正交谐波上；$|c_n|^2$ 是 $n$ 次谐波贡献的功率份额。**为什么核心**：在滤波设计里，"保留哪些谐波" ≡ "保留多少功率"——直接连到 SNR 计算。

### 周期谱与冲激串

周期信号的 [[fourier-transform]] 是**冲激串**（每 $\omega_0$ 一个 $\delta$）：

$$G(\omega) = 2\pi \sum_n c_n\,\delta(\omega - n\omega_0)$$

反之，**周期冲激串** $\delta_T(t) = \sum_k \delta(t-kT)$ 的 Fourier 级数系数是 $c_n = 1/T$（每个谐波振幅相同），FT 是等间距冲激串——这正是[[sampling-and-a-d-conversion]] 里采样定理的核心工具。

## 关联概念

- [[fourier-transform]] — 非周期版本；周期信号的 FT = 冲激串
- [[signals-and-lti-systems]] — 周期信号在 LTI 下的稳态响应
- [[discrete-fourier-transform-and-fft]] — 有限长离散版本
- [[sampling-and-a-d-conversion]] — 用周期冲激串刻画采样
- [[power-spectral-density]] — WSS 信号的谱表示
- [[functional-spaces]] — Fourier 基是 $L^2[0,T]$ 的完备正交基
