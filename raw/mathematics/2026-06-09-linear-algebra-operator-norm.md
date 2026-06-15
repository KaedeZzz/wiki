---
source: "KaedeSync/_Knowledge/Mathematics/Linear Algebra/Operator Norm.md"
ingested: 2026-06-09
---

A norm of a [[Matrix]] $\mathbf{A}$ is defined as:
$$
\lVert \mathbf{A} \rVert =\max_{\mathbf{x}\in \mathbb{C}^{n}\setminus \mathbf{0}} \frac{{\lVert \mathbf{Ax} \rVert }}{\lVert \mathbf{x} \rVert }
$$
therefore,
$$
\lVert \mathbf{Ax} \rVert \leq \lVert \mathbf{A} \rVert \lVert \mathbf{x} \rVert \quad \forall \mathbf{x}
$$
and
$$
\lVert \mathbf{AB} \rVert \leq \lVert \mathbf{A} \rVert \lVert \mathbf{B} \rVert
$$

[[Vector Norm]]