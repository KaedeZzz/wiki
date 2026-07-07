---
summary: PSD 是 WSS 随机过程功率在频率上的分布密度；Einstein-Wiener-Kitchin 定理 S(ω) = FT[R_X(k)] 说明 PSD 与自相关是 Fourier 对；实用估计是 (1/(2N+1)) |X^N(e^{jΩ})|² 在 N→∞ 下的期望，是 DTFT-squared。
tags: [communications, random-processes, spectrum]
updated: 2026-07-08
sources:
  - raw/communications/2026-07-08-discrete-basics-autocorrelation.md
  - raw/communications/2026-07-08-discrete-basics-autocorrelation-and-cross-correlation.md
  - raw/communications/2026-07-08-discrete-basics-discrete-time-white-noise.md
  - raw/communications/2026-07-08-continuous-basics-continuous-time-white-noise.md
  - raw/communications/2026-07-08-continuous-basics-frequency-domain-analysis-of-continuous-time-white-noise-with-finite-variance.md
  - raw/communications/2026-07-08-discrete-discrete-fourier-transform-and-fft-einstein-wiener-kitchin-theorem.md
  - raw/communications/2026-07-08-discrete-discrete-fourier-transform-and-fft-einstein-wiener-kitchin-theorem-explained.md
---

# 功率谱密度

## 定义

对**广义平稳**（WSS）随机过程 $\{X_t\}$，**自相关函数**：

$$R_X(k) = \mathbb{E}[X_t X_{t+k}] = \mathbb{E}[X_0 X_k]$$

（不显式依赖 $t$，是 WSS 的定义）。**功率谱密度**（PSD）：

$$S_X(e^{j\Omega}) = \sum_{k=-\infty}^{\infty} R_X(k)\,e^{-jk\Omega}$$

即 $R_X(k)$ 的 [[fourier-transform]]。$S_X$ 描述**功率在频率上的分布密度**：$\int_{-\pi}^{\pi} S_X\,d\Omega / (2\pi) = R_X(0) = \mathbb{E}[X_0^2]$（总功率）。

## 关键点

### 自相关的性质

- **偶对称**：$R_X(-k) = R_X(k)$
- **峰在原点**：$|R_X(k)| \leq R_X(0)$
- **非负**：$R_X(0) \geq 0$（$=$ 均方值）
- **半正定**：矩阵 $[R_X(i-j)]$ 半正定 → PSD 非负 $S_X \geq 0$

**Cauchy-Schwarz 直觉**：$X_t$ 与自己相关最强，与远远的样本相关最弱（对独立同分布 → $R_X(k) = 0$ for $k\neq 0$）。

### 互相关

对两 WSS 过程 $\{X_t\}, \{Y_t\}$：

$$R_{XY}(k) = \mathbb{E}[X_t Y_{t+k}]$$

一般**不对称** $R_{XY}(k) \neq R_{XY}(-k)$，但满足 $R_{XY}(-k) = R_{YX}(k)$。互功率谱 $S_{XY}(e^{j\Omega}) = \sum_k R_{XY}(k)e^{-jk\Omega}$——用于 [[optimal-filtering]] 的 Wiener 解。

### 白噪声

**白噪声**：$R_v(k) = \sigma_v^2\,\delta_{k0}$——在时间上完全**不相关**。PSD：

$$S_v(e^{j\Omega}) = \sigma_v^2 \qquad \forall\Omega$$

**功率均匀分布在整个频谱**（"白"的名字来源，与白光同理）。工程意义：**没有任何频段可以被预测**——最"无信息"的噪声，一切滤波理论的基准输入。

**连续时间白噪声**是理想化：$R_v(\tau) = \sigma_v^2\,\delta(\tau)$，PSD 常数 → **总功率无穷**。实际系统通过带宽限制变成"有限带宽白噪声"（带内平坦）。**Freq domain analysis**：即使加带宽约束，其 PSD 在带内仍平坦——这正当化了"白噪声 = 常量 PSD"的建模假设。

### Einstein-Wiener-Kitchin 定理

**PSD ≡ 有限段 DTFT 模平方的期望的极限**：

$$\lim_{N\to\infty} \mathbb{E}\!\left[\frac{1}{2N+1}\,|X^N(e^{j\Omega})|^2\right] = S_X(e^{j\Omega})$$

其中 $X^N(e^{j\Omega}) = \sum_{k=-N}^{N} X_k\,e^{-jk\Omega}$。

**含义**：*PSD 是（时间归一化的）DTFT 平方的期望值*——这是可**从数据估计** PSD 的核心公式。

**周期图法**（periodogram）：对有限观测 $\{X_0,\dots,X_{N-1}\}$，取

$$\hat S_X(e^{j\Omega}) = \frac{1}{N}\,|X_N(e^{j\Omega})|^2$$

作为 PSD 的估计。虽然是无偏（$N\to\infty$），但**方差不随 $N$ 减小**——是不一致估计。工程实践中用 **Welch 方法**（分段 + 加窗 + 平均）等改进。

### Wiener-Khinchin 定理（连续时间）

对连续时间 WSS 过程：

$$S_X(\omega) = \mathcal{F}\{R_X(\tau)\}(\omega)$$

即**自相关的 Fourier 变换**。名字 Wiener-Khinchin 与 Einstein-Wiener-Kitchin 是同一定理的不同署名传统（Wiener 独立于 Khinchin 及 Einstein 发现）。

### LTI 系统对 WSS 输入的响应

WSS 输入 $X_t$ 通过 LTI $H$：输出 $Y_t$ 也 WSS，且：

$$S_Y(e^{j\Omega}) = |H(e^{j\Omega})|^2\,S_X(e^{j\Omega})$$

$$R_Y(k) = R_X(k) * R_h(k),\quad R_h(k) = \sum_n h_n h_{n+k}$$

**关键工程公式**：滤波器改变 PSD 是**平方幅频响应加权**——线性滤波器不改变相位对功率的贡献。这条式子是所有基于统计的滤波器设计（[[optimal-filtering]]）的立足点。

### 应用速览

- **通信**：设计接收机匹配滤波要求已知信号能量与噪声 PSD
- **控制**：系统辨识用输入-输出的互功率谱估计频响
- **雷达/声呐**：目标回波 PSD 与背景噪声 PSD 之比 → 检测判据
- **医学信号**：EEG/ECG 频段能量分析
- **金融**：波动率与谱分析

## 关联概念

- [[random-processes]] — WSS 定义与背景
- [[fourier-transform]] — Wiener-Khinchin 的 FT 对
- [[discrete-fourier-transform-and-fft]] — 有限观测估计 PSD 用 FFT
- [[optimal-filtering]] — Wiener 频域解直接使用 PSD
- [[signals-and-lti-systems]] — WSS 通过 LTI 保持 WSS
- [[markov-chain]] — Markov 输入的 PSD 有特定形式
- [[hypothesis-testing]] — 白噪声下的检测理论用 PSD
