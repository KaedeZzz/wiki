---
summary: DFT 是有限长序列 → 有限长序列的酉变换 X_k=Σ x_n W^{kn}（W=e^{-j2π/N}）；FFT 用分治把 O(N²) 降到 O(N log N)；DFT 隐含周期扩展 → 时域是"循环卷积"而非线性卷积，需零填充或 Overlap-Save 才能实现快速线性卷积。
tags: [communications, dft, fft]
updated: 2026-07-08
sources:
  - raw/communications/2026-07-08-discrete-discrete-fourier-transform.md
  - raw/communications/2026-07-08-discrete-discrete-fourier-transform-and-fft-inverse-dft.md
  - raw/communications/2026-07-08-discrete-discrete-fourier-transform-and-fft-dft-matrix.md
  - raw/communications/2026-07-08-discrete-discrete-fourier-transform-and-fft-cyclic-properties-of-dft-matrix.md
  - raw/communications/2026-07-08-discrete-discrete-fourier-transform-and-fft-cyclic-properties-of-dft-matrix-1.md
  - raw/communications/2026-07-08-discrete-discrete-fourier-transform-and-fft-conjugate-symmetry-of-dft.md
  - raw/communications/2026-07-08-discrete-discrete-fourier-transform-and-fft-time-and-frequency-shift-properties-of-dft.md
  - raw/communications/2026-07-08-discrete-discrete-fourier-transform-and-fft-parsevals-theorem-for-dft.md
  - raw/communications/2026-07-08-discrete-discrete-fourier-transform-and-fft-circular-convolution-property-of-dft.md
  - raw/communications/2026-07-08-discrete-discrete-fourier-transform-and-fft-linear-convolution-from-circular-convolution.md
  - raw/communications/2026-07-08-discrete-discrete-fourier-transform-and-fft-overlap-and-save-method.md
  - raw/communications/2026-07-08-discrete-discrete-fourier-transform-and-fft-fast-fourier-transform.md
  - raw/communications/2026-07-08-discrete-discrete-fourier-transform-and-fft-radix-2-fft.md
  - raw/communications/2026-07-08-discrete-discrete-fourier-transform-and-fft-application-of-dft.md
---

# DFT 与 FFT

## 定义

对有限长序列 $\{x_n\}_{n=0}^{N-1}$，**DFT**：

$$X_k = \sum_{n=0}^{N-1} x_n\,W_N^{kn},\quad W_N = e^{-j2\pi/N}$$

**逆 DFT**：

$$x_n = \frac{1}{N}\sum_{k=0}^{N-1} X_k\,W_N^{-kn}$$

$\{X_k\}_{k=0}^{N-1}$ 是**长度 $N$** 的复序列——如把它周期延拓，得**周期 $N$** 的谱。矩阵化：$\mathbf{X} = \mathbf{F}\mathbf{x}$，$\mathbf{F}$ 是**DFT 矩阵**。

**FFT** 是用**分治**把 DFT 从 $O(N^2)$ 降到 $O(N\log N)$ 的算法族。

## 关键点

### DFT 矩阵与酉性

$$F_{k,n} = W_N^{kn}/\sqrt{N}$$

**酉**：$\mathbf{F}^H\mathbf{F} = \mathbf{I}$——列（或行）构成 $\mathbb{C}^N$ 的正交基（这就是"Fourier 向量"）。因此逆变换等价于共轭转置：$\mathbf{x} = \mathbf{F}^H \mathbf{X}$（用归一化因子 $1/\sqrt{N}$ 时）或除 $N$。

### 谱周期性

DFT 索引 $k$ 延拓到全体整数时，$W_N^{k(n+aN)} = W_N^{kn}$——谱在 $N$ 上周期。因此：

- 索引 $k = N/2$ 附近对应**最高数字频率** $\theta = \pi$
- $X_k$ 与 $X_{N-k}$ 是 Nyquist 对称的正负频率对

**实信号 → DFT 共轭对称**：$X_{N-k} = \overline{X_k}$——只需存储一半系数。

### 性质

| 时域 | 频域 |
|---|---|
| 线性 | 线性 |
| 时移 $x_{(n-m) \bmod N}$ | $W_N^{km} X_k$（相位斜坡） |
| 频移（时域调制）$W_N^{-nk_0} x_n$ | $X_{(k-k_0) \bmod N}$ |
| 循环卷积 $(x \circledast y)_n$ | $X_k Y_k$ |
| 相关 $\sum x_m^* y_{(m+n)\bmod N}$ | $\overline{X_k} Y_k$ |
| Parseval | $\sum |x_n|^2 = \tfrac{1}{N}\sum |X_k|^2$ |

**循环卷积**（$\circledast$）定义：$(x \circledast y)_n = \sum_{m=0}^{N-1} x_m\,y_{(n-m) \bmod N}$——所有下标模 $N$ 环绕。

### 循环 vs 线性卷积

**关键陷阱**：DFT 上的乘积对应的是**循环卷积**，不是**线性卷积**。信号处理中真正想要的是线性卷积（$y = h * x$，$y$ 的长度 $= L_h + L_x - 1$）。

**修复法**：把 $h$ 与 $x$ **零填充**到 $\geq L_h + L_x - 1$ 长度后再做 DFT。此时循环卷积 = 线性卷积。

**Overlap-Save 方法**：处理长信号 $x$ 与短滤波器 $h$（长度 $L_h$）时不必一次做整个 $L_x$ 长的 FFT。将 $x$ 分成有 $L_h - 1$ 重叠的块 → 每块做 DFT × $H$ × 逆 DFT → 丢弃前 $L_h - 1$ 个"污染"样本 → 拼接。**在极长信号上把复杂度从 $O(L_x L_h)$ 降到近似 $O(L_x \log L_h)$**——现代音频/DSP 系统的实时卷积基础。

### FFT 算法（Cooley-Tukey / Radix-2）

假设 $N = ML$（可因子化）。把 $\mathbf{x}$ 视为 $L \times M$ 的二维数组，索引 $k = lM + s$（内层），$n = mL + r$（外层）。经代数化简：

$$X_{mL+r} = \sum_{s=0}^{M-1} W_M^{sm}\,W_N^{sr}\,\underbrace{\sum_{l=0}^{L-1} x_{lM+s}\,W_L^{rl}}_{\text{列 DFT}}$$

**三步**：

1. 每列做 $L$-点 DFT（$M$ 次，$LM^2$ 次乘法）
2. 逐点乘 twiddle 因子 $W_N^{sr}$（$N = LM$ 次乘法）
3. 每行做 $M$-点 DFT（$L$ 次，$L^2 M$ 次乘法）

**总代价**：$ML(1 + M + L)$。若 $N = 2^k$，递归到底得 **Radix-2 FFT**：$O(N \log_2 N)$——相比朴素 $O(N^2)$ 在 $N = 10^6$ 时快约 $5 \times 10^4$ 倍。

### DFT 的三大应用

1. **频谱分析**：从有限观测估计信号频谱。窗函数 + FFT 是所有信号分析器的核心。
2. **快速卷积**：滤波、图像卷积（相关操作）通过 DFT 乘法比时域直接卷积快得多——用于混响、相关检测、图像处理。
3. **压缩与编码**：DCT（余弦变换，DFT 的实数亲戚）在 JPEG、MP3 里承担频域抽取；类似地 [[fourier-transform]] 与 [[fourier-series]] 是压缩的理论骨干。

## 关联概念

- [[fourier-transform]] — DTFT 是无限长离散序列的连续谱；DFT 是有限长版本
- [[fourier-series]] — FS 处理连续时间周期信号；DFT 处理离散时间周期序列
- [[z-transform]] — DTFT 是 z 变换在单位圆上取值；DFT 是 DTFT 的采样
- [[signals-and-lti-systems]] — 快速卷积让长 LTI 滤波实用化
- [[ofdm-and-isi]] — OFDM 直接把 IDFT/DFT 用作调制/解调
- [[fir-and-iir-filters]] — 时域滤波的 DFT 加速
- [[matrix-decomposition]] — DFT 矩阵是酉的，参与许多线性代数快速算法
