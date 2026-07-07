---
summary: Fourier 变换 F(ω)=∫f(t)e^{-jωt}dt 把能量信号从时域映到频域；Dirac δ 是奇异冲激，其"筛选性" ∫g(t)δ(t-a)dt=g(a) 是所有推导的杠杆；Heisenberg-Gabor TB≥1 揭示时频不可同时任意窄。
tags: [communications, fourier, frequency-domain]
updated: 2026-07-08
sources:
  - raw/communications/2026-07-08-continuous-fourier-transform-fourier-transform.md
  - raw/communications/2026-07-08-continuous-fourier-transform-discrete-time-fourier-transform-dtft.md
  - raw/communications/2026-07-08-continuous-fourier-transform-fourier-transform-and-laplace-transform.md
  - raw/communications/2026-07-08-continuous-basics-dirac-delta-function.md
  - raw/communications/2026-07-08-continuous-basics-sifting-property.md
  - raw/communications/2026-07-08-continuous-heisenberg-gabor-principle.md
  - raw/communications/2026-07-08-continuous-fourier-matrix.md
  - raw/communications/2026-07-08-continuous-fourier-vector.md
  - raw/communications/2026-07-08-continuous-matrix-representation-of-fourier-transforms.md
  - raw/communications/2026-07-08-discrete-z-transform-and-dtft-the-dtft-and-fourier-series.md
---

# Fourier 变换

## 定义

对**有限能量**信号 $f(t)$：

$$F(\omega) = \int_{-\infty}^{\infty} f(t)\,e^{-j\omega t}\,dt$$

**逆变换**：

$$f(t) = \frac{1}{2\pi}\int_{-\infty}^{\infty} F(\omega)\,e^{j\omega t}\,d\omega$$

$F(\omega)$ 是 $f$ 的**谱**，衡量各频率分量的复振幅。

## 关键点

### 核心性质表

| 时域 | 频域 |
|---|---|
| $\alpha f + \beta g$ | $\alpha F + \beta G$（线性） |
| $f(\alpha t)$ | $\tfrac{1}{|\alpha|}F(\omega/\alpha)$（**尺度反比** → Heisenberg-Gabor） |
| $f(t - t_0)$ | $F(\omega)\,e^{-j\omega t_0}$（时移） |
| $e^{j\omega_0 t}f(t)$ | $F(\omega - \omega_0)$（频移/调制） |
| $f^{(n)}(t)$ | $(j\omega)^n F(\omega)$（微分） |
| $f(t) * g(t)$ | $F(\omega)G(\omega)$（**卷积 → 乘积**） |
| $f(t) \cdot g(t)$ | $\tfrac{1}{2\pi} F * G$（乘积 → 卷积） |
| **对偶**：$f \leftrightarrow F$ | $F(t) \leftrightarrow 2\pi f(-\omega)$ |

**Parseval-Plancherel**：$\int |f|^2\,dt = \tfrac{1}{2\pi}\int |F|^2\,d\omega$——总能量守恒。

### Dirac Delta 与筛选性

$\delta(t)$ 定义为矩形脉冲面积保 1、宽度 $\to 0$ 的极限：

$$\delta(t) = \lim_{\epsilon\to 0} f_1(t; \epsilon),\quad \int_{-\infty}^{\infty}\delta(t)\,dt = 1,\quad \delta(t) = 0\ (t\neq 0)$$

其他构造：$\tfrac{\epsilon}{\epsilon^2\pi^2 + t^2}$（洛伦兹）、$\tfrac{\sin(at)}{\pi t}$（sinc；$a\to\infty$）。

**筛选性**（sifting property）：

$$\int_{-\infty}^{\infty} g(t)\,\delta(t - a)\,dt = g(a)$$

由此立即得 $\delta$ 的 FT 是 $1$（常值谱）；反之常值信号 $1$ 的 FT 是 $2\pi\delta(\omega)$（DC 分量）。**所有关于冲激的推导都建立在筛选性上**。

### FT 与 Laplace 变换的关系

**Fourier = Laplace 在虚轴上取值**：

$$F(\omega) = \left.G(s)\right|_{s = j\omega}$$

见 [[laplace-transform]]。区别：

- Laplace 处理 $t\geq 0$ 的**因果**信号并含衰减项 $e^{-\sigma t}$，能定义收敛半平面，适合分析瞬态与稳定性
- Fourier 处理**双侧**能量信号，只在稳态频率行为上有意义

对稳定系统，两者一致：极点在开左半平面 → Laplace 在虚轴收敛 → FT 存在。

### Heisenberg-Gabor 时频不确定性

对任意 $f(t)$，时长 $T$ 与频率带宽 $B$：

$$TB \geq 1$$

- 时域尖峰 → 频域宽（如 $\delta$ 的 FT 是全 1）
- 频域尖峰 → 时域宽（如 $e^{j\omega_0 t}$ 的 FT 是 $2\pi\delta(\omega-\omega_0)$）
- **Gaussian 是 $TB = 1$ 的极限最优形状**——同时最"紧"

后果：短时脉冲需要宽带；窄带信号必长——所有短时/瞬变分析（小波、STFT、语谱图）都在协调这个折衷。

### 离散时间 Fourier 变换（DTFT）

从**离散序列** $\{u_k\}$ 抽取**连续频率**谱：

$$U(\theta) = \sum_{k=-\infty}^{\infty} u_k\,e^{-jk\theta}$$

$U(\theta)$ 是 $\theta$ 的**周期 $2\pi$** 函数（因 $\theta \to \theta + 2\pi$ 时 $e^{-jk\theta}$ 不变）。

**三种视角**：

- 从**采样连续信号** $f_s(t) = \sum_n f(nT)\delta(t-nT)$ 的 FT：$F_s(\omega) = \sum_n f(nT)e^{-jn\omega T}$（连续信号谱的周期化，见 [[sampling-and-a-d-conversion]]）
- 从 [[z-transform]] 在**单位圆**上取值：$U(\theta) = U(z)\big|_{z = e^{j\theta}}$
- 从周期谱理论：DTFT 是 [[fourier-series]] 的对偶（角色互换）

**逆 DTFT**：$u_k = \tfrac{1}{2\pi}\int_{-\pi}^{\pi} U(\theta)\,e^{jk\theta}\,d\theta$。

**FS 与 DTFT 的关系**：DTFT 处理"离散时间 + 连续频率"，FS 处理"连续时间 + 离散频率"——两者互为对偶。

### 矩阵表示

有限长信号的 FT 变为 [[discrete-fourier-transform-and-fft]] 里的 DFT，可写为 $\mathbf{X} = \mathbf{F}\mathbf{x}$，$\mathbf{F}$ 是 **Fourier 矩阵** $F_{k,n} = e^{-j2\pi kn/N}/\sqrt{N}$——**酉矩阵**（$\mathbf{F}^H\mathbf{F} = \mathbf{I}$）。列向量 $\mathbf{f}_k$（**Fourier 向量**）互相正交，构成 $\mathbb{C}^N$ 的正交基。

## 关联概念

- [[fourier-series]] — 周期信号的 FT 是冲激串；FS 是 FT 的周期化对偶
- [[laplace-transform]] — FT = Laplace 在虚轴取值
- [[z-transform]] — DTFT = z 变换在单位圆取值
- [[discrete-fourier-transform-and-fft]] — 有限长离散版本
- [[sampling-and-a-d-conversion]] — 用 $\delta$ 串刻画采样、FT 说明频谱周期化
- [[signals-and-lti-systems]] — 卷积-乘积对偶是频域滤波的基础
- [[generating-functions]] — 特征函数就是 PDF 的 FT
- [[gaussian-distribution]] — Gaussian 是 Heisenberg 不等式的等号
