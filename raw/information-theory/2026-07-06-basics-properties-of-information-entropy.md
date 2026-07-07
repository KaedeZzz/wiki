---
source: KaedeSync/_Knowledge/Information Theory/Basics/Properties of Information Entropy.md
ingested: 2026-07-06
---

1. Non-negativity: $H(X)\geq 0$
2. If we denote the alphabet size of a random variable $X$ by $M=\lvert X \rvert$, then $H(X)\leq \log M$, where the equality is taken when $X$ is distributed *uniformly*.

Proof of second property:
$$
\begin{align}
H(X)-\log M&=\sum_{x}P(x)\log \frac{1}{P(x)}-\sum_{x}P(x)\log M \\
&= \sum_{x}P(x)\log \frac{1}{MP(x)} \\
\text{(change of basis) }&= \frac{1}{\ln 2}\sum_{x}P(x)\ln \frac{1}{MP(x)} \\
(\ln x\leq x-1\text{ for all }x)\ &\leq \frac{1}{\ln 2}\sum_{x}P(x)\left[\frac{1}{MP(x)}-1\right] \\
&=\frac{1}{\ln 2}\left[\sum_{x} \frac{1}{M}- \sum_{x} P(x)\right] \\
&= 0 
\end{align}
$$

[[Information Entropy]]