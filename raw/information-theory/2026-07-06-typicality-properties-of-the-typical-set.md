---
source: KaedeSync/_Knowledge/Information Theory/Typicality/Properties of the Typical Set.md
ingested: 2026-07-06
---

**Property 1:**
If $X^{n}=(X_{1},\dots,X_{n})$ is generated i.i.d. $\sim P$, then
$$
Pr(X^{n}\in A_{\epsilon, n})\overset {n \to \infty}\rightarrow 1
$$

**Property 2:**
Let $|A_{\epsilon,n}|$ denote the number of elements in the [[Typical Set]] $A_{\epsilon,n}$. Then:
$$
|A_{\epsilon,n}|\leq 2^{n(H(X)+\epsilon)}
$$

Property 3:
For sufficiently large $n$,
$$
|A_{\epsilon,n}|\geq(1-\epsilon)2^{n(H(X)-\epsilon)}
$$
