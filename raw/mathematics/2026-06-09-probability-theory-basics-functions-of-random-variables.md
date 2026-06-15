---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Basics/Functions of Random Variables.md"
ingested: 2026-06-09
---

[[Random Variable]]
Consider a projection: $\mathbb X\to\mathbb Y$. In general:

$$ P_Y(y)=\sum_{\{x|g(x)=y\}}P_X(x) $$

If $g$ is invertible (one-to-one map), then: $P_Y(y)=P_X(g^{-1}(y))$
CDF: $F_Y(y)=\mathbb P(g(X)\le y)$

PDF of $Y=aX+b$:
$$
f_Y(y)=\frac1{|a|}f_X(\frac{y-b}a)
$$

Inverting: for monotonic $g$,

$$ f_{Y=g(X)}(y)=\frac{f_X(g^{-1}(y))}{|g'(g^{-1}(y))|} $$

