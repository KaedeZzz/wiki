---
source: KaedeSync/_Knowledge/Information Theory/Coding/Source Coding/Coding Theorem for a Random Variable.md
ingested: 2026-07-06
---

[[Source Coding]]
Let $X$ be a random variable taking values in $\mathcal X$ with entropy $H(X)$. The [[Expected Code Length]] $L=\mathbb{E}\{\mathcal l(X)\}$ of any binary [[Prefix-free Code]] satisfies:
$$
L\geq H(X)
$$

Proof:
$$
\begin{align}
H(X)-L&=\sum_{i}p_{i}\log \frac{1}{p_{i}}-\sum_{i}p_{i}l_{i} \\
&=\sum_{i}\log \frac{2^{-l_{i}}}{p_{i}}=\frac{1}{\ln 2} \sum_{i}p_{i}\ln \frac{2^{-l_{i}}}{p_{i}} \\
&\overset{(a)}\leq\frac {1}{\ln 2}\sum_{i}p_{i}\left( \frac{2^{-l_{i}}}{p_{i}}-1 \right) \\
&= \frac{1}{\ln 2}\left( \sum_{i}2^{-l_{i}}-\sum_{i}p_{i} \right) \\
&\overset{(b)}\leq 1-1=0
\end{align}
$$
(a):

![[Natural Log Inequality]]

(b): [[Kraft Inequality]].
