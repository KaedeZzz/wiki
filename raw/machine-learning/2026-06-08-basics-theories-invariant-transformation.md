---
source: KaedeSync/_Knowledge/Machine Learning/Basics/Theories/Invariant Transformation.md
ingested: 2026-06-08
---

A transformation is invariant if the output of a function stays same for any transformation of input $X$, including no transformation:
$$
\text{For any }\phi, \quad F(X*\phi)=F(X)
$$
we generally assume that transforms follow group laws:
- there is always an inverse
$$
X=(X*\phi)*\phi^{-1}
$$
- A composition of two transformations can be represented as a single transformation
$$
(X*\phi_{1})*\phi_{2}=X*(\phi_{1}\phi_{2})
$$

Therefore, we can construct invariant network from non-invariant network. 

Assume we have non-invariant network $g:\mathbb{R}^{W\times H}\to \mathbb{R}^{O}$, then define
$$
f(X)=\max_{\phi}g(X*\phi)
$$
where the class with largest logit over all transformations is selected. Then
$$
\begin{align}
f(X*\phi) & =\max_{\phi'}g((X*\phi)*\phi') \\
 & =\max_{\phi'}g(X*(\phi \phi')) \\
 & =\max_{\phi'}g(X*\phi'')\quad \text{where }\phi''=\phi \phi' \\
 & =\max_{\phi''}g(X*\phi'') \\
 & =f(X)
\end{align}
$$

[[Machine Learning]]
