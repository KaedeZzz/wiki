---
summary: 多径信道让每个符号"抹到"数个输出上（ISI）。OFDM 用循环前缀把线性卷积变成循环卷积，再用 IDFT/DFT 把信道拆成 N 个独立子载波——每个子载波的补偿只是"除以一个复数"，是现代 Wi-Fi、LTE、5G、DVB 的基础。
tags: [communications, modulation, isi]
updated: 2026-07-08
sources:
  - raw/communications/2026-07-08-inter-symbol-inference-isi.md
  - raw/communications/2026-07-08-discrete-discrete-fourier-transform-and-fft-avoiding-inter-symbol-interference.md
  - raw/communications/2026-07-08-discrete-discrete-fourier-transform-and-fft-avoiding-inter-symbol-interference-1.md
  - raw/communications/2026-07-08-discrete-discrete-fourier-transform-and-fft-orthogonal-frequency-domain-modulation-ofdm.md
---

# OFDM 与符号间干扰

## 定义

**符号间干扰**（Inter-Symbol Interference, ISI）：多径（回波）信道 $h$ 使输出 $y = h * x$——每个发射符号被"抹到"数个输出上；接收端难以从 $y$ 中恢复 $x$。

**正交频分复用**（OFDM）：把信号切成块 + 添加**循环前缀**（cyclic prefix），使实际信道效果变成**循环卷积**（[[discrete-fourier-transform-and-fft]]），从而在 DFT 域上信道被对角化——每个子载波独立均衡。

## 关键点

### ISI 的物理机制

无线信道有多条传播路径（直射 + 反射 + 折射）——每条延迟不同。发射符号 $x_n$ → 接收得到 $y_n = \sum_k h_k\,x_{n-k}$。若 $h$ 长度 $L$（**信道时延扩展**），则 $y_n$ 混合了 $x_n$ 到 $x_{n-L+1}$ 共 $L$ 个符号。**符号率越高、时延扩展越大** → ISI 越严重 → 直接影响误码率。

### 传统对策：均衡器

在时域直接反卷积——用**均衡滤波器** $g$ 使 $g * h \approx \delta$。缺点：

- 极小信道零点附近 $g$ 增益爆炸 → 噪声放大
- 时变信道要在线自适应
- 复杂度高

### OFDM 的核心技巧：循环前缀

1. 把要发送的比特分组成 **DFT 块** $X_0, \dots, X_{N-1}$（每个 $X_k$ 是一个子载波的调制符号）
2. **IDFT** → 时域块 $x_0, \dots, x_{N-1}$
3. **循环前缀**：把块**末尾的 $L$ 个样本**复制到块**开头**——发送 $L + N$ 长的信号：$[x_{N-L}, x_{N-L+1}, \dots, x_{N-1}, x_0, x_1, \dots, x_{N-1}]$

**为什么这样做**：假设信道 $h$ 长度 $\leq L$。接收信号 $y = h * (\text{prefix + 块})$。**去掉前 $L$ 个样本后**，剩下的 $N$ 个 $y$ 样本恰是块 $x$ 与信道 $h$ 的**循环卷积**：

$$y_n = (x \circledast h)_n,\quad n = 0, 1, \dots, N-1$$

**关键**：循环前缀让线性卷积在这 $N$ 个样本上等效为循环卷积。

### DFT 域上信道对角化

对块 DFT：

$$Y_k = X_k\,H_k$$

其中 $H_k$ 是信道频响 $H(e^{j2\pi k/N})$。**信道在子载波域退化为逐点乘法** → 每个子载波独立均衡：

$$\hat X_k = Y_k / H_k$$

**单符号除法就是每个子载波的均衡器**——ISI 消除的极简做法。这是 OFDM 之所以在时变多径信道下大获成功的根本原因。

### 系统总揽

**发射端**：比特 → 编码 → 星座映射 → IDFT → 加循环前缀 → 数模转换 → 上变频
**信道**：多径 + AWGN
**接收端**：下变频 → 采样 → 去循环前缀 → DFT → 逐载波均衡 → 星座解映射 → 解码

**性能优势**：

- **多径抗性**：只要 $L$ 足够长，信道任意时延扩展都被吸收
- **子载波灵活**：可以按子载波 SNR 分配比特（**Water-filling**）
- **FFT 高效**：整个调制/解调是 $O(N\log N)$

**代价**：

- **循环前缀开销**：$L/(L+N)$ 的带宽/时间损失
- **高峰均比（PAPR）**：$N$ 个正弦叠加使包络幅度大，功放需大动态范围
- **载波间干扰（ICI）**：频偏或多普勒破坏子载波正交性

### 应用

**Wi-Fi**（802.11a/g/n/ac/ax）、**LTE / 5G NR** 下行、**DVB-T/T2** 数字电视、**ADSL** / **DOCSIS**——过去 25 年宽带无线/有线通信的**统治性调制方式**。

## 关联概念

- [[discrete-fourier-transform-and-fft]] — 循环卷积性质是 OFDM 的核心
- [[signals-and-lti-systems]] — ISI 就是 LTI 信道对符号序列的作用
- [[fir-and-iir-filters]] — 单载波传统均衡就是 IIR/FIR 反卷积
- [[optimal-filtering]] — Matched Filter 是单载波检测的极限
- [[channel-capacity]] — Water-filling 用于 SNR 变频段的容量最优功率分配
- [[channel-coding]] — OFDM 通常与 LDPC/Turbo 码级联
- [[ldpc-codes]] — 5G 长码的选择
