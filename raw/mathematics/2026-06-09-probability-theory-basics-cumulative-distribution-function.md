---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Basics/Cumulative Distribution Function.md"
ingested: 2026-06-09
---

[[Random Variable]]
Cumulative distribution function:

$$
\begin{align}
F_{X}(x)&=P(X\leq x)  \\
&\implies f_{X}(x)=\frac{d}{dx}F_{X}(x) \\
&\implies F_{X}(x)=\int_{-\infty}^{x}f_{X}(x)dx
\end{align}
$$

The following properties follow directly from the axioms of probability:

![[Pasted image 20241101110316.png]]
Specifically note that, 
$$
\lim_{ y \to \infty }F_{XY}(x,y)=F_{X}(x)
$$
A random variable is *continuous* if its distribution function can be written:
$$
F(x)=\int_{-\infty}^{x}f(u)du
$$
for some $0\leq f(u)<\infty$.

Two random variables are independent if:
$$
F_{XY}(x,y)=F_{X}(x)F_{Y}(y)
$$
