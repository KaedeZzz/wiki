---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Basics/Sampling Multivariate Gaussian.md"
ingested: 2026-06-09
---

#ESSENTIAL 
[[Multivariate Gaussian]] and [[Distribution Sampling]]
To sample $\vec{y}\sim \mathcal N(\vec{ u},  \mathbf{\Sigma})$:
1. find $\mathbf{A}$ s.t. $\mathbf{AA}^{T}=\mathbf{\Sigma}$;
2. sample $\vec{ x}$ from i.i.d. $\{\mathcal N(0,1)\}^{n}$
3. $\vec{ y}=\mathbf{A}\vec{x}+\vec{ u}$
