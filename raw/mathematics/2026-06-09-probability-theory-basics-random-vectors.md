---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Basics/Random Vectors.md"
ingested: 2026-06-09
---

[[Random Variable]]

Random vectors:
Let $X_{1},X_{2},\dots,X_{n}$ be $n$ continuous (or discrete) random variables.
We call $X=(X_{1},X_{2},\dots,X_{n})\in \mathbb{R}^n$ a continuous (or discrete) random vector.

joint PDF:
$$
P(X_{1}\in A_{1},\dots,X_{n}\in A_{n})=\int_{-\infty}^\infty \mathbb{I}_{A_{n}}(x_{n})\dots\int_{-\infty}^\infty \mathbb{I}_{A_{1}}(x_{1})f(x_{1},\dots,x_{n})dx_{1}\dots dx_{n}
$$

$i$-th marginal:
$$
f_{X_{i}}(x_{i})=\int_{-\infty}^\infty\dots\int_{-\infty}^\infty f(x_{1},\dots,x_{n})dx_{1}\dots dx_{i-1}dx_{i+1}\dots dx_{n}
$$

[[Independence]]:
$$
f(x_{1},\dots,x_{n})=f_{X_{1}}(x_{1})\dots f_{X_{n}}(x_{n}).
$$

![[Independent Expectations]]

change of variables:
$$
\begin{bmatrix}
Y_{1} \\
\vdots \\
Y_{n}
\end{bmatrix}
=
\begin{bmatrix}
g_{1}(X_{1}\dots X_{n}) \\
\vdots \\
g_{n}(X_{1}\dots X_{n}) 
\end{bmatrix}
\to
Y=G(X)
$$
If $G$ invertible: $X=G^{-1}(Y)=H(Y)$
