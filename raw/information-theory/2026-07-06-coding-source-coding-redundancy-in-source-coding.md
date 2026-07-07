---
source: KaedeSync/_Knowledge/Information Theory/Coding/Source Coding/Redundancy in Source Coding.md
ingested: 2026-07-06
---

[[Source Coding]]
Often the true distribution of the source is unknown, and we have to work with an estimated source distribution for compression.

Suppose the true PMF of a random variable is $P$ and estimated PMF is $\hat{P}$.
Designed code length satisfy:
$$
l_{i}=\log \frac{1}{\hat{p}_{i}}
$$
therefore, [[Expected Code Length]]:
$$
L=\sum_{i}p_{i}\log \frac{1}{\hat{p}_{i}}=\sum_{i}p_{i}\log \frac{1}{p_{i}}+\sum_{i}p_{i}\log \frac{p_{i}}{\hat{p}_{i}}=H(P)+D(P||\hat{P})
$$
Therefore $D(P||\hat{P})$ is the *redundancy* in bits per symbol.

![[Minimax Redundancy]]