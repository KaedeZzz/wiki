---
summary: 信道编码定理：DMC 上任意速率 R<C 可达（联合典型解码 + 随机码本），任意 R>C 不可行（Fano 逆定理）。线性块码和 Hamming/重复码是最基本的构造；最优 BSC 解码 = 最小 Hamming 距离。
tags: [information-theory, coding, communication]
updated: 2026-07-06
sources:
  - raw/information-theory/2026-07-06-coding-channel-coding-channel-coding.md
  - raw/information-theory/2026-07-06-coding-channel-coding-length-n-code.md
  - raw/information-theory/2026-07-06-coding-channel-coding-block-code.md
  - raw/information-theory/2026-07-06-coding-channel-coding-rate-of-code.md
  - raw/information-theory/2026-07-06-coding-channel-coding-linear-block-code.md
  - raw/information-theory/2026-07-06-coding-channel-coding-linear-block-codes-as-subspaces.md
  - raw/information-theory/2026-07-06-coding-channel-coding-hamming-distance.md
  - raw/information-theory/2026-07-06-coding-channel-coding-7,4-hamming-code.md
  - raw/information-theory/2026-07-06-coding-channel-coding-repetition-coding.md
  - raw/information-theory/2026-07-06-coding-channel-coding-parity-coding.md
  - raw/information-theory/2026-07-06-basics-channel-coding-theorem.md
  - raw/information-theory/2026-07-06-coding-channel-coding-channel-coding-theorem-for-bsc.md
  - raw/information-theory/2026-07-06-coding-channel-coding-channel-coding-theorem-idea-of-channel-rate-for-dmc.md
  - raw/information-theory/2026-07-06-coding-channel-coding-channel-coding-theorem-joint-typical-encoding.md
  - raw/information-theory/2026-07-06-coding-channel-coding-channel-coding-theorem-average-probability-of-error-of-code.md
  - raw/information-theory/2026-07-06-coding-channel-coding-channel-coding-theorem-maximal-probability-of-error-of-code.md
  - raw/information-theory/2026-07-06-coding-channel-coding-channel-coding-theorem-probability-of-error-of-a-code.md
  - raw/information-theory/2026-07-06-coding-channel-coding-channel-coding-theorem-proof-of-achievability,-channel-coding-theorem.md
  - raw/information-theory/2026-07-06-coding-channel-coding-channel-coding-theorem-proof-of-maximum-rate,-channel-coding-theorem.md
  - raw/information-theory/2026-07-06-coding-channel-coding-channel-information-lemma.md
  - raw/information-theory/2026-07-06-coding-channel-coding-ldpc-optimal-decoding-of-block-code.md
  - raw/information-theory/2026-07-06-coding-channel-coding-ldpc-optimal-decoding-of-bsc.md
  - raw/information-theory/2026-07-06-coding-channel-coding-ldpc-optimal-bsc-decoding-power.md
  - raw/information-theory/2026-07-06-coding-channel-coding-ldpc-minimum-distance-of-code.md
  - raw/information-theory/2026-07-06-coding-channel-coding-ldpc-minimum-distance-of-lbc.md
  - raw/information-theory/2026-07-06-coding-channel-coding-ldpc-minimum-distance-property-of-lbc.md
---

# 信道编码

## 定义

在 [[channel-capacity]] 描述的信道 $(\mathcal{X},\mathcal{Y},P_{Y|X})$ 上：**编码**将 $k$ 个信息比特映射到 $n$-长码字（$n$ 次信道使用），**解码**根据接收 $Y^n$ 猜测原消息。

$(n,k)$ 码：$2^k = 2^{nR}$ 个消息，**速率** $R = \tfrac{k}{n} = \tfrac{1}{n}\log_2 M$ 比特/次使用。目标：速率高 + 错误率低 + 编解码可算。

## 关键点

### 错误概率

**平均**（消息均匀）：$\bar P_e = \tfrac{1}{2^{nR}}\sum_j\Pr(\hat W\neq j|W=j)$
**最大**：$P_e^{(\max)} = \max_j \Pr(\hat W\neq j|W=j)$

（最大有界 $\Rightarrow$ 平均有界，但反之不然——证明中常用"扔掉最差一半码字"技巧从平均转到最大。）

### 信道编码定理（Shannon 1948）

对任意 DMC，$C = \max_{P_X} I(X;Y)$：

- **可达性**：任意 $R < C$、任意 $\epsilon>0$，存在充分大 $n$ 的 $(n,k=nR)$ 码使 $P_e^{(\max)} < \epsilon$。
- **逆定理**：若一族码的 $P_e^{(n)} \to 0$，则必有 $R \leq C$。

**BSC(f)** 的特例：$C = 1 - \mathcal{H}_2(f)$；对 $f=0.1$ 的信道，$C\approx 0.53$，即每次信道使用最多传约 0.53 比特信息。

### 可达性证明（随机码本 + 联合典型解码）

**随机码本**：每个码字每一位独立按容量达成的 $P_X$ 采样。码本是 $2^{nR}\times n$ 随机矩阵。

**联合典型解码**：接收 $Y^n$，找唯一使 $(X^n(\hat W), Y^n)$ 联合典型的 $\hat W$（无唯一者则出错）。

**误差分解**：设发送 $W=1$，令 $E_k$ 为"码字 $k$ 与 $Y^n$ 联合典型"事件：

$$\bar P_e \leq \Pr(E_1^c) + \sum_{k\neq 1}\Pr(E_k)$$

- $\Pr(E_1^c) \to 0$：$(X^n(1),Y^n)\sim P_{XY}$，[[typicality-and-aep]] 的联合 AEP 保证。
- $\sum_{k\neq 1}\Pr(E_k) \leq 2^{nR}\cdot 2^{-n(I(X;Y)-3\epsilon)}$：错的码字 $X^n(k)$ 独立于 $Y^n$，联合 AEP 给出**指数级小**的偶然典型概率。

组合：只要 $R < I(X;Y) - 3\epsilon = C - 3\epsilon$，$\bar P_e < 2\epsilon$。用 $\bar P_e$ 存在 $\Rightarrow$ 具体码本存在 $\Rightarrow$ 扔掉最差一半得到 $P_e^{(\max)} < 4\epsilon$、速率 $R - \tfrac{1}{n}$。

关键动作："pick every symbol of every codeword i.i.d. from capacity-achieving distribution"——这是 Shannon 编码理论最惊人的想法：**随机码通常最优**。

### 逆定理（Fano 界）

用 [[mutual-information]] 里的 Fano 不等式加上**信道信息引理** $I(X^n;Y^n) \leq nC$：

$$nR = H(W) = H(W|\hat W) + I(W;\hat W) \leq (1 + P_e nR) + I(X^n;Y^n) \leq 1 + P_e nR + nC$$

$$\Rightarrow P_e \geq 1 - \tfrac{C}{R} - \tfrac{1}{nR}$$

若 $R > C$，则 $P_e$ 不趋于零 → 反证。

### 线性块码

$(n,k)$ 线性块码：$\mathbf{c} = \mathbf{x}G$（在 GF(2) 上），$G$ 是 $k\times n$ **生成矩阵**。所有码字组成 $\{0,1\}^n$ 的 $k$-维**子空间**（$G$ 的行是一组基）。

**系统形式** $G = [I_k | P]$：前 $k$ 位就是原信息位，后 $n-k$ 位是校验位 $\mathbf{x}P$。任意 $G$ 可通过初等行变换转换为系统形式（码字集合不变，仅映射改变）。

**校验矩阵** $H = [P^T | I_{n-k}]$：$GH^T = 0$；码字 $\mathbf{c}$ 满足 $\mathbf{c}H^T = \mathbf{0}$。$H$ 的行是子空间 $\mathcal{C}$ 的正交补基。

### 具体码

- **重复码** $\mathcal{R}_m$：每位重复 $m$ 次；速率 $\tfrac{1}{m}$；多数表决解码；错误概率服从 [[discrete-distributions]] 的二项分布。
- **奇偶校验**：每 8 位加 1 校验位；能检 1 位错但不能纠。
- **(7,4) Hamming 码**：4 信息位 + 3 校验位（每校验位由 3 个信息位的模 2 加），可**纠正任意 1 位错**。这是最经典的可纠错码。

### Hamming 距离与解码

$d(\mathbf{x},\mathbf{y})$ = 两向量不同位置的数量。**线性码的最小距离**：

$$d_{\min} = \min_{\mathbf{c}\neq\mathbf{0}} \text{wt}(\mathbf{c})$$

（用 $d(\mathbf{c}_i,\mathbf{c}_j) = \text{wt}(\mathbf{c}_i + \mathbf{c}_j)$；LBC 的线性性使得码字差仍是码字。）

**校验矩阵视角**：$d_{\min}$ = 使 $H$ 的这些列的模 2 加为 $\mathbf{0}$ 的**最小列数**。

**最优解码**（对任意信道）：极大似然 $\hat{\mathbf{c}} = \arg\max_{\mathbf{c}} \Pr(\mathbf{y}|\mathbf{c})$。

**BSC 特化**（$p<1/2$）：

$$\Pr(\mathbf{y}|\mathbf{c}) = (1-p)^n\left(\tfrac{p}{1-p}\right)^{d(\mathbf{y},\mathbf{c})}$$

单调递减 $\Rightarrow$ ML = **最小 Hamming 距离解码**。可纠正任意 $t \leq \lfloor(d_{\min}-1)/2\rfloor$ 个错。

## 关联概念

- [[channel-capacity]] — 编码定理的可达上界
- [[mutual-information]] — Fano 不等式是逆向的核心
- [[typicality-and-aep]] — 联合 AEP 给出可达性证明
- [[fundamental-subspaces]] — 线性码是 GF(2) 上的子空间
- [[eigendecomposition]] — 线性代数背景
- [[ldpc-codes]] — 现代高性能信道码
- [[source-coding]] — 通信的另一半：先压缩后传输
