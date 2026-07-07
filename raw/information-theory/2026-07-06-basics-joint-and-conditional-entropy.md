---
source: KaedeSync/_Knowledge/Information Theory/Basics/Joint and Conditional Entropy.md
ingested: 2026-07-06
---

Joint [[Information Entropy]]:
$$
H(X,Y)=-\sum_{x \in X}\sum_{y \in Y}\log f(x,y)=\sum_{x,y}P_{XY}(x,y)\log \frac{1}{P_{XY}(x,y)}
$$
Conditional Entropy:
$$
\begin{align}
H(Y|X)&=\sum_{x,y}P_{XY}(x,y)\log \frac{1}{P_{Y|X}(y|x)} \\
&=\sum_{x}P_{X}(x)\sum_{y}P_{Y|X}(y|x)\log \frac{1}{P_{Y|X}(y|x)} \\
&=\sum_{x}P_{X}(x)H(Y|X=x) \\
\end{align}
$$
"How much entropy is decreased in knowing $X$"

A relationship: $H(X, Y)-H(X)=H(Y|X)$
Proof:
$$
\begin{align}
H(X,Y)&=\sum_{x,y}P(x,y)\log \frac{1}{P(x,y)} \\
&=\sum_{x,y}P(x,y)\left[\log \frac{1}{P(x)}+ \log \frac{1}{p(y|x)}\right] \\
&=H(X)+H(Y|X)
\end{align}
$$
If $X$ and $Y$ are independent, $H(Y|X)=H(Y)$

![[Chain Rule of Joint Entropy]]
