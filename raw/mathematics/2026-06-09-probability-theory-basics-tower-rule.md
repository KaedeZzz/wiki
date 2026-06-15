---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Basics/Tower Rule.md"
ingested: 2026-06-09
---

Also known as: *Law of iterated expectation*
$$
\mathbb{E}\{Y\}=\mathbb{E}\{\mathbb{E}\{Y|X\}\}
$$
Proof:
$$
\begin{aligned}
\mathbb{E}\{ r(X,Y) \}&=\int_{-\infty}^\infty\int_{-\infty}^\infty r(x,y)f_{XY}(x,y)dxdy\\ 
&=\int_{-\infty}^\infty\left( \int_{-\infty}^\infty r(x,y)f_{X|Y}(x|y)dx\right)f_{Y}(y)dy\\ 
&=\int_{-\infty}^\infty \mathbb{E}\{ r(X,Y)|Y=y \}f_{Y}(y)dy\\
&=\mathbb{E}\{ \mathbb{E}\{ r(X,Y)|Y=y \} \}
\end{aligned}
$$

