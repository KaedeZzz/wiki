---
source: "KaedeSync/_Knowledge/Mathematics/Linear Algebra/Operator Ip-Norm.md"
ingested: 2026-06-09
---

Defining [[Operator Norm]]s to be different [[Ip-Norm]].

$\lVert \mathbf{A} \rVert_{1}$:
$$
\begin{align}
\lVert \mathbf{A} \rVert_{1} =\max_{\mathbf{x}\in \mathbb{C}^{n}\setminus \mathbf{0}} \frac{{\lVert \mathbf{Ax} \rVert_{1} }}{\lVert \mathbf{x} \rVert_{1} }  & = \max_{j}\sum_{i=1}^{n}\lvert a_{ij} \rvert
\end{align}
$$
How to derive this? #SUPO 

$\lVert \mathbf{A} \rVert_{n}$:
$$
\begin{align}
\lVert \mathbf{A} \rVert_{\infty} =\max_{\mathbf{x}\in \mathbb{C}^{n}\setminus \mathbf{0}} \frac{{\lVert \mathbf{Ax} \rVert_{\infty} }}{\lVert \mathbf{x} \rVert_{\infty} }  & = \max_{i}\sum_{j=1}^{n}\lvert a_{ij} \rvert
\end{align}
$$

$\lVert \mathbf{A} \rVert_{2}$:
$$
\begin{align}
\lVert \mathbf{A} \rVert_{2}^{2} =\max_{\mathbf{x}\in \mathbb{C}^{n}\setminus \mathbf{0}} \frac{{\lVert \mathbf{Ax} \rVert_{2}^{2} }}{\lVert \mathbf{x} \rVert_{2}^{2} }  & = \max \frac{{\mathbf{x}^{H}\mathbf{A}^{H}\mathbf{Ax}}}{\mathbf{x}^{H}\mathbf{x}}
\end{align}
$$
note that the maximum occurs for largest eigenvalue of $\mathbf{A}^{H}\mathbf{A}$:
$$
\lVert \mathbf{A} \rVert_{2}^{2}=\frac{{\mathbf{x}^{H}\lambda_{\max}(\mathbf{A}^{H}\mathbf{A})\mathbf{x}}}{\mathbf{x}^{H}\mathbf{x}}=\lambda_{\max}(\mathbf{A}^{H}\mathbf{A})
$$
the non-negativity of norm is guaranteed by non-negativity of eigenvalue of a [[Positive Semi-Definite]] matrix $\mathbf{A}^{H}\mathbf{A}$.

If $\mathbf{A}$ is [[Hermitian]], then $\lVert \mathbf{A} \rVert_{2}=\lvert \lambda \rvert_{\max}(\mathbf{A})$.