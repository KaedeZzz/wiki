---
source: "KaedeSync/_Knowledge/Mathematics/Measure Theory/Lebesgue Integral.md"
ingested: 2026-06-09
---

Consider the bounded function $f(x)$ defined on an abstract set $X$ such that $0\leq f_{min}\leq f(x)\leq f_{max}$. 
Given a partition $f_{min}=f_{1}<f_{2}<\dots<f_{n+1}=f_{max}$, there will be set of values of $x$ such that $f_{k}\leq f(x)< f_{k+1}$ for $x \in X_{k}$. 
Denote the [[Measure]] of $X_{k}$ as $\mu(X_{k})$, the Lebesgue integral is defined as:

$$
\int_{X}fd\mu=\lim_{ \max|f_{k}-f_{k-1}| \to 0 } \sum_{k=1}^{n}f_{k}\mu(X_{k})
$$
