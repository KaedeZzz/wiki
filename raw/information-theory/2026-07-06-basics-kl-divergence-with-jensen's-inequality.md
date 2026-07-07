---
source: KaedeSync/_Knowledge/Information Theory/Basics/KL Divergence with Jensen's Inequality.md
ingested: 2026-07-06
---

#ESSENTIAL 

[[KL Divergence]] and [[Jensen's Inequality]]

$$
\begin{align}
D(P||Q)&=\sum_{x}P(x)\log_{2} \frac{P(x)}{Q(x)} \\
&=\sum_{x}P(x)-\log_{2}  \frac{Q(x)}{P(x)} \\
 & =\mathbb{E}\left[ -\log_{2} \frac{Q(X)}{P(X)} \right] \\
  & \geq-\log_{2} \mathbb{E}\left[  \frac{Q(X)}{P(X)}  \right] \\
 & =-\log_{2}\left( \sum_{x}P(x) \frac{Q(x)}{P(x)} \right) \\
 & =-\log_{2}\left( \sum_{x}Q(x) \right) \\
 & =-\log_{2}1=0
\end{align}

$$
