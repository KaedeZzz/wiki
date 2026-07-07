---
summary: 信道容量 C=max_P_X I(X;Y) 是可靠通信的最大速率；BSC 容量为 1-H₂(f)；连续 AWGN 通道的 Shannon-Hartley 公式 C=B log(1+SNR) 是数字通信设计的核心工具。
tags: [information-theory, channel]
updated: 2026-07-06
sources:
  - raw/information-theory/2026-07-06-basics-channel-capacity.md
  - raw/information-theory/2026-07-06-basics-binary-symmetric-channel.md
  - raw/information-theory/2026-07-06-basics-shannon-hartley-theorem.md
  - raw/information-theory/2026-07-06-coding-channel-coding-binary-channel.md
  - raw/information-theory/2026-07-06-coding-channel-coding-discrete-memoryless-channel.md
---

# 信道容量

## 定义

对给定信道 $Q = P_{Y|X}$，**容量**为最大化输入-输出互信息：

$$C_Q = \max_{P_X} I(X;Y)$$

达到最大的分布称为**最优输入分布**。信道编码定理（见 [[channel-coding]]）告诉我们：$C$ 恰是"任意低错误率下可传输的最大信息率"。

## 关键点

### 离散无记忆信道（DMC）

由三元组 $(\mathcal{X}, \mathcal{Y}, P_{Y|X})$ 定义：

$$P_{Y|X}(b|a) = \Pr(Y = b | X = a)$$

"给定当前输入，输出只依赖于当前输入"（[[markov-chain]] 意义上的无记忆）。$n$ 次使用后：

$$P_{Y^n|X^n}(y^n|x^n) = \prod_{i=1}^n P_{Y|X}(y_i|x_i)$$

### 二元对称信道 BSC(f)

- $\Pr(Y=1|X=0) = \Pr(Y=0|X=1) = f$（**翻转概率**）
- $\Pr(Y=0|X=0) = \Pr(Y=1|X=1) = 1-f$

容量：

$$C_{\text{BSC}} = 1 - \mathcal{H}_2(f)$$

（其中 $\mathcal{H}_2$ 为二元熵函数，见 [[information-entropy]]）。$f=1/2$ 时 $C=0$（信道全是噪声），$f=0$ 或 $1$ 时 $C=1$。

### 二元擦除信道 BEC(ε)

输入 $\{0,1\}$，输出 $\{0, 1, ?\}$，擦除概率 $\epsilon$。容量 $C_{\text{BEC}} = 1 - \epsilon$；LDPC 通过消息传递可以逼近这个极限（见 [[ldpc-codes]]）。

### Shannon-Hartley 定理（连续 AWGN）

带宽 $B$、平均信号功率 $S$、平均噪声功率 $N$ 的加性白高斯信道：

$$C = B\log_2\!\left(1 + \frac{S}{N}\right) \quad\text{bits/s}$$

**推导要点**（用 [[differential-entropy]]）：AWGN 下 $Y = X + N$，$I(X;Y) = h(Y) - h(Y|X) = h(Y) - h(N)$。给定功率约束，$h(Y)$ 由最大微分熵定理在 $Y$ 高斯时取最大 → 最优 $X$ 也是高斯。代入高斯的微分熵公式即得。

工程意义：SNR 每翻倍，容量线性增加 $B$ 比特/秒；这条曲线是所有现代通信系统（Wi-Fi、蜂窝、光纤）的设计基线。

### 优化视角

$C = \max_{P_X} I(X;Y)$ 是**凸优化**：$I(X;Y)$ 作为 $P_X$ 的函数是凹的（见 [[convexity]]），可用 Blahut-Arimoto 算法数值求解。

## 关联概念

- [[mutual-information]] — 容量是互信息在输入分布上的最大值
- [[differential-entropy]] — Shannon-Hartley 推导用最大微分熵定理
- [[gaussian-distribution]] — AWGN 最优输入为高斯
- [[information-entropy]] — BSC 容量含二元熵函数
- [[channel-coding]] — 编码定理告诉我们 $C$ 是可达上界
- [[ldpc-codes]] — 逼近 BEC 容量的实用码
- [[convexity]] — 容量优化是凸的
