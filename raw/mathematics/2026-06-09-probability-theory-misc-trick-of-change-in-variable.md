---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Misc/Trick of Change in Variable.md"
ingested: 2026-06-09
---

#ESSENTIAL 
[[Transformation of Random Variable]]

Mainly from EP1 Q6.
Say $X=g(U)$. When solving for $f_{X}(x)$ from $f_{U}(u)$, always do:
$$
\begin{align}
F_{X}(x)=P(X\leq x)=P(g(U)\leq X)=\text{some form of } F_{U}(h(x))
\end{align}
$$
Then differentiate with respect to $x$. 

Note that, $\int_{-\infty}^{\infty} f_{X}(x)=1$.