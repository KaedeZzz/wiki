---
source: KaedeSync/_Knowledge/Information Theory/Typicality/Jointly Typical.md
ingested: 2026-07-06
---

The set $A_{\epsilon,n}$ of *jointly typical* sequences $\{ (x_{n},y_{n}) \}$ with respect to a joint PMF $P_{XY}$ is defined as
$$
\begin{align}
A_{\epsilon,n}=\{ &(x_{n,y_{n}})\in\mathcal X^{n}\times\mathcal Y^{n}\text{ such that} \\
&|-\frac{1}{n}\log P_{X}(x^{n})-H(X)|<\epsilon, \\
&|-\frac{1}{n}\log P_{Y}(y^{n})-H(Y)|<\epsilon, \\
&|-\frac{1}{n}\log P_{XY}(x^{n},y^{n})-H(X,Y)|<\epsilon \}
\end{align}
$$

[[Typical Set]]