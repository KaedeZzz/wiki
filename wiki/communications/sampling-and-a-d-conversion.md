---
summary: 采样把连续信号 f(t) 变成 {f(nT)}，频谱变周期化 F_s(ω)=(1/T)Σ F(ω-nω_0)；Nyquist 定理要求采样率 ω_0 ≥ 2ω_{max} 避免混叠。C→D 转换有多种映射（Euler/后向差分/双线性），双线性 s=(2/T)(z-1)/(z+1) 是唯一同时保持稳定和有理性的选择，代价是频率轴的 tan(θ/2) 扭曲。
tags: [communications, sampling, dac]
updated: 2026-07-08
sources:
  - raw/communications/2026-07-08-basics-sampling.md
  - raw/communications/2026-07-08-discrete-basics-normalised-sampling.md
  - raw/communications/2026-07-08-digital-and-analog-conversion-c2d-stability-theorem.md
  - raw/communications/2026-07-08-digital-and-analog-conversion-continuous-to-discrete-algebraic-transformations.md
  - raw/communications/2026-07-08-digital-and-analog-conversion-frequency-warping.md
  - raw/communications/2026-07-08-digital-and-analog-conversion-impulse-invariance.md
  - raw/communications/2026-07-08-digital-and-analog-conversion-ramp-invariance.md
  - raw/communications/2026-07-08-digital-and-analog-conversion-response-matching.md
  - raw/communications/2026-07-08-digital-and-analog-conversion-step-invariance.md
  - raw/communications/2026-07-08-discrete-digital-filtering-proof-of-c2d-stability-theorem-for-bilinear-transformation.md
---

# 采样与模数转换

## 定义

**采样**：以周期 $T$ 采样连续信号 $f(t)$，得到离散序列 $\{f(nT)\}_{n=-\infty}^{\infty}$。**模拟-数字转换**（A/D）先做采样，再量化。**归一化采样**：把采样周期 $T$ 归一为 $1$（即用**数字频率** $\theta = \omega T$ 描述离散信号）。

**连续-离散（C2D）算法**：把连续时间传递函数 $H_c(s)$ 映到离散 $H(z)$，通常表为 $H(z) = H_c(s)|_{s = \psi(z)}$，即选择一个 $s = \psi(z)$ 的映射。

## 关键点

### 采样定理（Nyquist-Shannon）

采样信号 $f_s(t) = \sum_n f(nT)\delta(t - nT) = f(t)\,\delta_T(t)$，其中 $\delta_T$ 是周期 $\delta$ 串。由 [[fourier-series]]，$\delta_T$ 系数是 $c_n = 1/T$，所以

$$f_s(t) = \frac{1}{T}\sum_n f(t)\,e^{jn\omega_0 t}\qquad(\omega_0 = 2\pi/T)$$

取 [[fourier-transform]]：

$$F_s(\omega) = \frac{1}{T}\sum_{n=-\infty}^{\infty} F(\omega - n\omega_0)$$

**采样把连续频谱周期化**——每 $\omega_0$ 复制一份。

**Nyquist**：若 $F(\omega) = 0$ for $|\omega| > \omega_{\max}$（带限信号），只要 $\omega_0 \geq 2\omega_{\max}$（**Nyquist 率**），各周期化副本不重叠，$F$ 可从 $F_s$ 完美恢复（低通滤波 + 缩放）。

**混叠**（aliasing）：$\omega_0 < 2\omega_{\max}$ → 高频副本折入低频 → 失真不可逆。工程上必须在 A/D 前接**抗混叠滤波器**（低通到 $\omega_0/2$）。

### 归一化采样与 DTFT

数字频率 $\theta = \omega T \in [-\pi, \pi]$。连续频率 $\omega \in [0, \omega_0/2]$ 映到数字 $\theta \in [0, \pi]$。DTFT 的**周期 $2\pi$** 恰对应连续谱的**周期 $\omega_0$**——两个视角同构。

采样后的 DTFT 与连续 FT 的关系：$U(\theta) = \sum_k f(kT)e^{-jk\theta}$，与 $F_s(\omega)|_{\omega=\theta/T}$ 一致（相差归一化）。

### C→D 算法映射（$s = \psi(z)$）

从 $z = e^{sT}$（精确关系）泰勒展开：

$$z = 1 + sT + \tfrac{(sT)^2}{2} + \dots$$

各种截断给不同映射：

| 映射 | $\psi(z)$（$s = \psi(z)$） | 稳定保持？ |
|---|---|---|
| **前向差分（Euler）** | $s = (z - 1)/T$ | ❌ |
| **后向差分** | $s = (z - 1)/(zT) = (1 - z^{-1})/T$ | ✅ |
| **双线性（Tustin）** | $s = (2/T)\,(z-1)/(z+1)$ | ✅ |

**为什么不用更高阶多项式截断**：反解 $z = \psi^{-1}(s)$ 变复杂；把每个 $z$ 替换成 $s$ 的多项式会**爆炸极点/零点数**——简单连续设计变复杂离散设计。双线性用一阶有理保持简洁 + 稳定。

### C→D 稳定性定理

**后向差分**与**双线性变换**作用于稳定连续系统 → 稳定离散系统。

**前向差分（Euler）不保稳定**：连续极点在左半 $s$ 平面可能被映到 $|z| > 1$。

**双线性的证明要点**：连续稳定 ⇔ 极点 $\text{Re}(s) < 0$；双线性 $z = \tfrac{2/T + s}{2/T - s}$ 是**共形映射**，把左半 $s$ 平面映到单位圆内 $|z| < 1$——严格保持稳定。见 [[stability]]。

### 频率扭曲（Frequency Warping）

双线性变换的代价：**频率轴非线性映射**。

$$G(e^{j\theta}) = G_c\!\left(\frac{e^{j\theta} - 1}{e^{j\theta} + 1}\right) = G_c\!\left(j\tan\frac{\theta}{2}\right)$$

**数字频率 $\theta$ 对应模拟频率 $\omega = \tan(\theta/2)$**。低频 ($\theta \ll 1$) 近似线性 $\omega \approx \theta/2$；高频接近 $\theta = \pi$ 时 $\omega \to \infty$——整个模拟频率轴 $[0, \infty)$ 被压缩到 $[0, \pi]$。

**工程补救**：设计前**预扭曲**——把想要的数字截止频率 $\theta_c$ 反映射到模拟 $\omega_c^{\text{pre}} = \tan(\theta_c/2)$，用它设计连续原型，再做双线性映射 → 实际数字截止频率就在 $\theta_c$。

### 时域不变映射家族

**基于响应保持**的另一族方法：

| 方法 | 保持不变的响应 |
|---|---|
| **Impulse Invariance** | $h[n] = T\,h_c(nT)$ — 冲激响应 |
| **Step Invariance** | 阶跃响应 |
| **Ramp Invariance** | 斜坡响应 |
| **Response Matching** | 更一般的响应形式 |

**Impulse Invariance** 会产生**混叠**（若原型不严格带限），实际中受限；Step Invariance 更常用（含零阶保持 ZOH 建模）。这些方法**不映射频率轴**（无扭曲），但只在某类信号上精确保持行为。

### 选择原则

- **数字滤波器设计**：几乎总用**双线性**（唯一同时稳定 + 简洁 + 全频率一一对应）
- **数字控制器**：需匹配连续控制器行为时用 **step invariance**（阶跃是控制系统最常见的输入）
- **仿真数字化**：impulse invariance 或 ZOH 用于把连续动力学离散化，配合小 $T$ 使混叠可忽略

## 关联概念

- [[fourier-transform]] — 采样定理的推导工具
- [[fourier-series]] — $\delta_T$ 的 FS 展开是采样定理的起点
- [[z-transform]] — 离散域的对应变换；$z = e^{sT}$
- [[laplace-transform]] — 连续原型所在的域
- [[stability]] — C→D 映射的稳定性保持是核心考察
- [[fir-and-iir-filters]] — IIR 滤波器的设计多用双线性从模拟原型转换
- [[frequency-response]] — 扭曲的模拟/数字频率对应
