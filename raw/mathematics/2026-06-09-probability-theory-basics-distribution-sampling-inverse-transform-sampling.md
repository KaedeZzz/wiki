---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Basics/Distribution Sampling/Inverse Transform Sampling.md"
ingested: 2026-06-09
---

Assume we can compute the inverse to the cdf, $H^{-1}(x)$.
1. Let $U\sim \text{Uniform}(0,1)$
2. Return $H^{-1}(U)$ 

**Key idea: $H^{-1}(U)$ is distributed as $h(x)$**

*Proof:*
Let $X=H^{-1}(U)$, by change of variables formula, 
$$
f_{X}(x)=f_{U}(H(x)) \frac{dH}{dx}=\frac{dH}{dx}=h(x)
$$
