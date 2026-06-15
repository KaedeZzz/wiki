---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Basics/Proof of the Central Limit Theorem.md"
ingested: 2026-06-09
---

Let's denote $S_{n}=\sum_{n}f_{n}$ where each $f_{n}=f(x_{n})$ has a mean of zero and variance $\sigma_{f}^{2}$.
Moment generating function for each $f_{n}$ is $M_{f}(t)=\mathbb{E}\{e^{tX}\}$
Moment generating function for $Z_{N}=\frac{S_{N}}{\sqrt{ N\sigma_{f}^{2} }}$ is a power of the individual function $M_{f}$: 
$$
M_{Z_{N}}(t)=\left( M_{f}\left(\frac{t}{\sqrt{ N\sigma_{f}^{2} }}\right) \right)^{N}
$$
Expansion of Taylor series gives:
$$
\begin{align}
M_{Z_{N}}(t) & =\left( \mathbb{E}\left\{  e^{\frac{tX}{\sqrt{ N\sigma_{f}^{2}}}} \right\} \right)^{N} \\
 & =\left( \mathbb{E}\left\{ 1+\frac{tX}{\sqrt{ N\sigma_{f}^{2}}}+\frac{\left( \frac{tX}{\sqrt{ N\sigma_{f}^{2}}} \right)^{2}}{2}+\dots \right\} \right)^{N} \\
 \text{truncate taylor series}& =\left( 1+0+\frac{{t^{2}}\mathbb{E}[X^{2}]}{2N\sigma_{f}^{2} }+\epsilon_{N}\right)^{N} \\
 & =\left( 1+\frac{t^{2}}{2N} \right)^{N}
\end{align}
$$
therefore, as $N$ approaches $\infty$, the expression approaches $e^{\frac {t^{2}} {2}}$, which implies that $\frac{\sum_{n}f_{n}}{\sqrt{ N\sigma _{f}^{2} }}$ has mean $0$ and variance $1$.

[[The Central Limit Theorem]]