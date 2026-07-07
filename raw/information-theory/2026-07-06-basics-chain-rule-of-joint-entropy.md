---
source: KaedeSync/_Knowledge/Information Theory/Basics/Chain Rule of Joint Entropy.md
ingested: 2026-07-06
---

$$
\begin{align}
H(X_{1},X_{2},\dots,X_{n})&=H(X_{1})+H(X_{2}|X_{1})+\dots+H(X_{n}|X_{n-1},\dots,X_{1}) \\
&=\sum_{i=1}^{n}H(X_{i}|X_{i-1},\dots,X_{1})
\end{align}
$$