---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Estimators/Standard Mean Estimator.md"
ingested: 2026-06-09
---

An obviously good way to estimate mean is to take average of the samples.
$$
\hat{\mu}= \frac{1}{N}\sum_{i=1}^{N}x_{i}
$$
How do we know this is a good estimator? One way is to say that it is unbiased:

![[Unbiased Estimator]]
$$
\begin{aligned}
\mathbb{E}\{\hat{\mu}\}&=\mathbb{E}\left\{ \frac{1}{N}\sum_{i=1}^{N}x_{i} \right\} \\
&= \frac{1}{N} \mathbb{E}\left\{\sum_{i=1}^{N}x_{i} \right\} \\
&= \mu
\end{aligned}
$$
Therefore the standard mean estimator is unbiased.

Variance of the standard mean estimator:
$$
\begin{align}
\text{Var}[\hat{\mu}]&=\mathbb{E}\{\hat{\mu}^{2}\}-\mathbb{E}\{\hat{\mu}\}^{2} \\
&= \mathbb{E}\{\hat{\mu}^{2}\}-\mu^{2}
\end{align}
$$
Assume each signal symbol being independent of each other, then
$$
\begin{align}
\mathbb{E}\{\hat{\mu}^{2}\}&=\frac{1}{N^{2}}\sum_{j=1}^{N}\sum_{i=1}^{N}\mathbb{E}[X_{i}X_{j}] \text{ where }\mathbb{E}[X_{i}X_{j}]=
\begin{cases}
\mathbb{E}\{X_{i}^{2}\}=\mu ^{2}+\sigma ^{2},\quad &i=j \\
\mu ^{2},\quad &i\neq j
\end{cases}
\end{align}
$$
Therefore, we have in total
$$
\begin{align}
\mathbb{E}\{\hat{\mu}^{2}\}&= \frac{1}{N^{2}}(N^{2}\mu ^{2}+ N\sigma ^{2}) \\
&=\mu ^{2}+ \frac{\sigma ^{2}}{N}
\end{align}
$$
Hence: $\text{Var}[\hat{\mu}]= {\sigma ^{2}}/{N}$
We see that variance tends to zero as $N$ tends to infinity.
