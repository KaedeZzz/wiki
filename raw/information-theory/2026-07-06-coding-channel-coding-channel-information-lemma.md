---
source: KaedeSync/_Knowledge/Information Theory/Coding/Channel Coding/Channel Information Lemma.md
ingested: 2026-07-06
---

Let $Y^{n}$ be the result of passing a sequence $X^{n}$ through a [[Discrete Memoryless Channel]] of channel capacity $\mathcal C$. Then
$$
\begin{align}
I(X^{n};Y^{n}) & =H(Y^{n})-H(Y^{n}|X^{n}) \\
 & =H(Y^{n})-\sum_{i=1}^{n}H(Y_{i}|Y_{i-1},\dots,Y_{1},X^{n}) \\
 & =H(Y^{n})-\sum_{i=1}^{n}H(Y_{i}|X_{i}) \\
 & \leq \sum_{i=1}^{n}H(Y_{i})-\sum_{i=1}^{n}H(Y_{i}|X_{i}) \\
 & =\sum_{i=1}^{ n}I(X_{i};Y_{i})\leq n\mathcal C 
\end{align}
$$

Consider any $(2^{nR},n)$ channel code with average probability of error $P_{e}$. Let $W$ be the encoded message uniform over $\{ 1,\dots,2^{nR} \}$, we have:
$$
\begin{align}
nR & =H(W) \\
 & =H(W|\hat{W})+I(W;\hat{W}) \\
 & \leq 1+P_{e}nR +I(W;\hat{W}) \\
 & \leq 1+P_{e}nR + I(X^{n};Y^{n}) \\
 & \leq 1+P_{e}nR+n\mathcal C
\end{align}
$$
Thus,
$$
P_{e}\geq 1-\frac{C}{R}-\frac{1}{nR}
$$
therefore, unless $R\leq C$, $P_{e}$ is bounded away from $0$ as $n\to \infty$.