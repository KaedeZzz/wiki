---
source: KaedeSync/_Knowledge/Information Theory/Basics/KL Divergence.md
ingested: 2026-07-06
---

**Kullback-Leibler Divergence** (between two distributions); also known as relative entropy.

$$
D_{KL}(P||Q)=\sum_{i}P(i)\log \frac{P(i)}{Q(i)}
$$
KL divergence measures the "distance" between distributions $P$ and $Q$, but it is not a true distance, for which it does not follow exchange rule: $D(P||Q)\neq D(Q||P)$

KL Divergence is **non-negative**.
Proof:
$$
\begin{align}
-D(P||Q)&= \frac{1}{\ln 2}\sum_{x \in \mathcal X}P(x)\ln \frac{Q(x)}{P(x)} \\
 & \leq\frac{1}{\ln 2}\sum_{x \in \mathcal X}P(x)\left( \frac{Q(x)}{P(x)}-1 \right)=0
\end{align}
$$
where the following inequality is used:

![[Natural Log Inequality]]


[[Information Theory]], [[Information Entropy]]