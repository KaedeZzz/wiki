---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Basics/Random Sum of Distributions.md"
ingested: 2026-06-09
---

#ESSENTIAL 
Let $N$ be a random integer with [[Generation Function]] $G_{N}(z)=\mathbb{E}\{z^{N}\}$.
Let $X_{i}$ be iid with generation function $G_{X}(z)$.
Let $S=\sum_{i=1}^{N}X_{i}$.
$$
\begin{align}
G_{S}(z)&=\mathbb{E}\{z^{S}\}\overset{\text{Law of iter. exp.}}=\mathbb{E}\{\mathbb{E}\{z^{S}|N\}\} \\
&=\mathbb{E}\{G_{X}(z)^{N}\}=G_{N}(G_{X}(z))
\end{align}

$$