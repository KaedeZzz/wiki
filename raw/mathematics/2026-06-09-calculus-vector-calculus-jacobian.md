---
source: "KaedeSync/_Knowledge/Mathematics/Calculus/Vector Calculus/Jacobian.md"
ingested: 2026-06-09
---

Let $\mathbf{X}=H(\mathbf{Y})$, that is,
$$
\begin{bmatrix}
X_{1} \\
\vdots \\
X_{n}
\end{bmatrix}
=
\begin{bmatrix}
h_{1}(Y_{1},\dots,Y_{n}) \\
\vdots \\
h_{n}(Y_{1},\dots,Y_{n})
\end{bmatrix}
$$

The Jacobian is defined as:

$$
\begin{align}
\mathbf{J}(\mathbf{y})&=\frac{{\partial \mathbf{J}}}{\partial \mathbf{y}}=
\begin{bmatrix}
\frac{\partial}{\partial y_{1}}h_{1}&\dots&\frac{\partial}{\partial y_{n}}h_{1} \\
\vdots&\ &\vdots \\
\frac{\partial}{\partial y_{1}}h_{n}&\dots&\frac{\partial}{\partial y_{n}}h_{n}
\end{bmatrix} \\ \\
\end{align}
$$
That is,
$$
\begin{align}
[J]_{ij}&= \frac{\partial h_{i}}{\partial y_{j}}\\ \\
&\implies
f_{Y}(y)=f_{X}(H(y))|\det J(y)|
\end{align}
$$
[[Vector Gradient]]