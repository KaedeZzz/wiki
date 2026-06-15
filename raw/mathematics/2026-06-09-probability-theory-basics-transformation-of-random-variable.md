---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Basics/Transformation of Random Variable.md"
ingested: 2026-06-09
---

For two [[Random Variable]]s $X,Y$, let $Y=r(X)$. if $r$ is invertible and increasing:
$$
\begin{align}
x&=r^{-1}(r(x)) \\ \\
F_{Y}(y)&=P(Y\leq y) \\
&=P(X\leq r^{-1}(y)) \\
&=F_{X}(r^{-1}(y))
\end{align}
$$

Differentiate both sides with respect to $y$ to obtain:

$$
f_{Y}(y)=f_{X}(r^{-1}(y)) \frac{d}{dy}r^{-1}(y)
$$