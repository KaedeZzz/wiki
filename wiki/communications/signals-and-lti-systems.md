---
summary: 信号处理的语法层：连续/离散信号、LTI 系统（线性 + 时不变）、因果性（h_k=0 for k<0）、有界性、周期性；离散 LTI 由差分方程或冲激响应完全刻画，poles/zeros 结构与控制理论共享。
tags: [communications, signal-processing, lti]
updated: 2026-07-08
sources:
  - raw/communications/2026-07-08-basics-signals.md
  - raw/communications/2026-07-08-basics-linear-time-invariant-lti.md
  - raw/communications/2026-07-08-basics-causal.md
  - raw/communications/2026-07-08-basics-periodic.md
  - raw/communications/2026-07-08-basics-signals-as-differential-equations.md
  - raw/communications/2026-07-08-discrete-basics-bounded-signal.md
  - raw/communications/2026-07-08-discrete-basics-discrete-time-signals.md
  - raw/communications/2026-07-08-discrete-basics-delta-response.md
  - raw/communications/2026-07-08-discrete-basics-semi-infinite-sequence.md
  - raw/communications/2026-07-08-discrete-basics-poles-and-zeros-of-discrete-lti-system.md
  - raw/communications/2026-07-08-discrete-basics-steady-state-response-of-discrete-system-to-sinusoidal-input.md
  - raw/communications/2026-07-08-discrete-basics-final-value-theorem-for-step-response.md
  - raw/communications/2026-07-08-continuous-basics-signal-power-and-energy.md
---

# 信号与 LTI 系统

## 定义

**信号**：时间（或空间）的函数——连续时间 $x(t)$ 或离散序列 $\{x_k\}$。

**LTI 系统**：满足两条性质的算子 $L$：

- **线性**：$L(\alpha_1 u + \alpha_2 u') = \alpha_1 L(u) + \alpha_2 L(u')$
- **时不变**：$L(u_{k+m}) = y_{k+m}$（输入延迟 $m$ 步，输出也延迟 $m$ 步）

## 关键点

### 冲激响应与卷积表示

离散 LTI 完全由**冲激响应** $\{h_k\}$（对 $\delta_k$ 的输出）刻画。任意输入的输出：

$$y_t = \sum_{k=-\infty}^{\infty} h_k\,x_{t-k} = (h * x)_t$$

即输入与冲激响应的**离散卷积**——LTI 的一切频域/时域分析都建立在这个公式上。连续时间版本 $y(t) = (h * x)(t) = \int h(\tau)x(t-\tau)\,d\tau$。

### 因果性

系统因果 ⇔ **冲激响应 $h_k = 0$ for $k < 0$**——输出只依赖当前及过去输入，不依赖未来。物理系统必然因果；实时数字滤波器也必须因果；离线信号处理可以用非因果滤波器（零相位处理）。

### 时不变 + 稳定 → 频响

LTI + 稳定 + 输入正弦 $e^{j\omega t}$ → 稳态输出仍是同频正弦 $H(\omega)e^{j\omega t}$，$H(\omega)$ 是**频率响应**。对离散：正弦输入 $e^{j\theta k}$ → 输出 $G(e^{j\theta})e^{j\theta k}$。这正是 [[frequency-response]] 的定义。

### 输入 WSS → 输出 WSS

若输入是**广义平稳**过程（[[random-processes]]），LTI 输出也是 WSS——保持二阶统计结构。输出的功率谱密度 = $|H(\omega)|^2 \times$ 输入 PSD，见 [[power-spectral-density]]。

### 离散 LTI 的 poles/zeros

用 z-变换（见 [[z-transform]]、[[z-transform-discrete-systems]]）：

$$G(z) = \frac{b_0 + b_1 z^{-1} + \dots + b_m z^{-m}}{1 + a_1 z^{-1} + \dots + a_n z^{-n}}$$

化正幂后分子分母同为 $\max(m,n)$ 次多项式 → 各有 $\max(m,n)$ 根。**FIR 特例**：$G(z) = b_0 + b_1 z^{-1} + \dots + b_m z^{-m}$，所有极点在 $z=0$（原点），系统**天生稳定**（见 [[fir-and-iir-filters]]）。

### 因果 vs 有限支撑

**有界信号**：$|u_k| \leq M$ 存在。**半无限序列**：$k$ 从 $0$ 开始（右侧无限）。这两个概念在 z-变换的收敛域讨论里核心：**因果+稳定** ⇔ **单位圆外所有极点在圆内**（右侧信号的常见情形）。

### 稳态正弦响应与终值定理

**稳态**：对稳定 LTI 系统输入 $\cos(\omega n)$，输出经过瞬态后趋于 $|G(e^{j\omega})|\cos(\omega n + \angle G(e^{j\omega}))$。工程测量：向电路灌入正弦扫频、测幅频/相频 → 直接给出 $G(e^{j\omega})$。

**终值定理**（离散）：$\lim_{n\to\infty} y_n = \lim_{z\to 1}(z-1)Y(z)$（前提：所有极点在 $|z|<1$ 内、可能有 $z=1$ 的孤立极点）。用于计算阶跃响应的稳态值，也是控制系统跟踪能力的一站式判据。

### 信号能量与功率

**能量信号**：$\int |x(t)|^2\,dt < \infty$（可用 [[fourier-transform]] 表示；Parseval：能量在时域 = 频域）。

**功率信号**：能量无限但时间平均功率有限，$\lim_{T\to\infty} \tfrac{1}{2T}\int_{-T}^{T}|x|^2\,dt < \infty$——周期信号和 WSS 随机过程属此类，用 [[fourier-series]] 或 PSD 表示。

### 周期性

**周期** $T$：$x(t+T) = x(t)$。周期信号可展成 [[fourier-series]]；非周期能量信号用 [[fourier-transform]]；采样后离散信号用 DTFT 或 [[discrete-fourier-transform-and-fft]]。

### 信号即差分方程

离散 LTI 也可表示为线性差分方程：

$$y_n + a_1 y_{n-1} + \dots + a_p y_{n-p} = b_0 u_n + b_1 u_{n-1} + \dots + b_q u_{n-q}$$

用 [[z-transform]] 把差分方程变为代数方程 $(1 + a_1 z^{-1} + \dots)Y(z) = (b_0 + b_1 z^{-1} + \dots)U(z)$，直接读出传递函数 $G(z) = Y/U$。

## 关联概念

- [[fourier-transform]] / [[fourier-series]] — LTI 在频域的表示
- [[z-transform]] — 离散 LTI 的自然工具
- [[frequency-response]] — 控制论中的等价概念
- [[transfer-function]] — 通用传递函数
- [[fir-and-iir-filters]] — 具体的离散 LTI 实现
- [[random-processes]] — WSS 输入信号
- [[power-spectral-density]] — WSS 信号在频域的统计描述
- [[sampling-and-a-d-conversion]] — 连续 ↔ 离散的桥梁
