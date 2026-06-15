---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Time Series Analysis/Basics/ARMA Process.md"
ingested: 2026-06-09
---

Let $\{ W_{t} \}$ be white noise such that:
$$
\begin{align}
\mathbb{E}\{ W_{t} \}&=0 \\
R_{W}(k)&=\delta_{0,k}\omega_{W}^{2}
\end{align}
$$
Then $ARMA(p,q)$ is the process where
$$
X_{t}=\sum_{i=1}^{p}a_{i}X_{t-i}+\sum_{i=0}^{q}b_{i}W_{t-i}
$$
We often assume $b_{0}=1$.
*notice different summation constants.*

$ARMA(p,q)$ can be represented as the output of an [[Linear Time-Invariant (LTI)]] stimulated with [[White Noise]]. Hence, it is [[Wide-Sense Stationary]].

[[Auto-Regressive (AR) Process]], [[Moving Average (MA) Process]]