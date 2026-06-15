---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Random Processes/Additive White Gaussian Noise (AWGN) Channel.md"
ingested: 2026-06-09
---


Continuous-time  AWGN Channel:
$$
Y(t)=X(t)+N(t)
$$
Usual assumptions on the channel:
1. Input $X(t)$ is **power-limited** to $P$
2. $X(t)$ is **band-limited** to $W$
3. Noise $N(t)$ is a random process assumed to be [[White Gaussian Noise]]

Through [[Shannon-Nyquist Sampling Theorem]], it can be shown that the continuous-time channel
$$
Y(t)=X(t)+N(t)
$$
with power constraint $P$ and bandwidth constraint $W$ is equivalent to the following discrete-time channel:
$$
Y_{k}=X_{k}+Z_{k}
$$
with:
- average power constraint $P$
- $Z_{k}$ are i.i.d. [[Gaussian Distribution]] with mean $0$ and variance $\sigma ^{2}$

###### AWGN Capacity

$$
\begin{align}
I(X;Y) & =h(Y)-h(Y|X) \\
 & =h(Y)-h(X+Z|X) \\
 & =h(Y)-h(Z|X) \\
 & =h(Y)-h(Z)
\end{align}
$$
1. $h(Z)=\frac{1}{2}\log 2\pi e\sigma ^{2}$
2. Note that 
$$
\begin{align}
\mathbb{E}Y^{2}=\mathbb{E}(X+Z)^{2} & =\mathbb{E}X^{2}+2\mathbb{E}(XZ)+\mathbb{E}Z^{2} \\
 & =\mathbb{E}X^{2}+\sigma ^{2}
\end{align}
$$
which implies
$$
\mathbb{E}X^{2}\leq P\implies \mathbb{E}Y^{2}\leq P+\sigma ^{2}
$$
![[Maximum Differential Entropy Theorem]]

Therefore:
$$
\begin{align}
h(Y) & \leq \frac{1}{2}\log 2\pi e(P+\sigma ^{2}) \\
I(X;Y) & =h(Y)-\frac{1}{2}\log 2\pi e \sigma ^{2} \\
 & =\frac{1}{2} \log\left( 1+\frac{P}{\sigma ^{2}} \right)
\end{align}

$$
where $\frac{P}{\sigma ^{2}}$ is known as the [[Signal-to-Noise Ratio (SNR)]].

If the channel has bandwidth $W$, it can be used $2W$ times per second. Therefore, the capacity in bits per sec is:
$$
2W \cdot \frac{1}{2}\log\left( 1+ \frac{P}{\sigma ^{2}} \right)=W\log\left( 1+ \frac{P}{\sigma ^{2}} \right) \text{ bits/sec}
$$

Why can AWGN capacity be larger than $1$? #SUPO 