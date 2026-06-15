---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Time Series Analysis/Basics/Auto-Regressive (AR) Process.md"
ingested: 2026-06-09
---

Let $\{ W_{t} \}$ be [[White Noise]] such that:
$$
\begin{align}
\mathbb{E}\{ W_{t} \}&=0 \\
R_{W}(k)&=\delta_{0,k}\omega_{W}^{2}
\end{align}
$$
Auto-Regressive process $AR(p)$ is:
$$
X_{t}=\left( \sum_{i=1}^pa_{i}X_{t-i}\right)+W_{t}
$$
where $p$ is the order of the process.

AR1 process:
$$
\begin{aligned}
X_{n}&=aX_{n-1}+W_{n}=a^{2}X_{n-2}+aW_{n-1}+W_{n}\\
&=\sum_{k=0}^\infty W_{n-k}a^k=\sum_{k=0}^\infty W_{n-k}h_{k}
\end{aligned}
$$
Note that this is a [[Discrete Convolution]] process.
Therefore, AR1 is [[Causal]] with impulse response $h_{k}$.
*Mean:* 
$$
\mathbb{E}\{ X_{n} \}=\sum_{k=0}^\infty \mathbb{E}\{W_{n-k}h_{k}\}=0\text{ since }\mathbb{E}\{ W_{n} \}=0
$$
*Variance:*
$$
\mathbb{E}\{X_{n}^2\}=\sum_{n=0}^\infty \mathbb{E}\{W_{n-k}^2\}a^{2k}+\text{ cross terms }=\sum_{n=0}^\infty \sigma ^{2}a^{2k}=\frac{\sigma ^{2}}{1-a^{2}}\text{ given }|a|<1
$$

Note that $AR(p)$ process is [[Wide-Sense Stationary]].

[[Random Processes]], [[Time Series Analysis]]