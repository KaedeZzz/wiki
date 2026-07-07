---
source: KaedeSync/_Knowledge/Information Theory/Coding/Channel Coding/LDPC/Parity Check Matrix.md
ingested: 2026-07-06
---

[[Linear Block Code]]

The orthogonal complement of $\mathcal C$, denoted $\mathcal C^{\perp}$, is defined as the set of all vectors in $\{ 0,1 \}^{n}$ that are orthogonal to each vector in $\mathcal C$.

It can be shown that $\mathcal C^{\perp}$ is also a subspace with dimension $n-k$. Therefore, we can find a basis of it, denoting as
$$
H=\begin{bmatrix}
\underline{h}_{1} \\
\vdots \\
\underline{h}_{n-k}
\end{bmatrix}
$$
this $(n-k)\times n$ matrix is called the parity check matrix. Each codeword $\underline{c}\in \mathcal C$ is orthogonal to each row of $H$, therefore
$$
\begin{align}
\underline{c}H^{T}=0 \\
GH^{T}=0
\end{align}
$$

How to find $H$?
$$
H=[P^{T}|I_{n-k}]
$$
because, recall that $P$ is $k\times(n-k)$:
$$
GH^{T}=
\begin{bmatrix}
I_{k} | P
\end{bmatrix}
\begin{bmatrix}
P \\
I_{n-k}
\end{bmatrix}
=P+P=0
$$