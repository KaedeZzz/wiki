---
source: "KaedeSync/_Knowledge/Mathematics/Linear Algebra/Error Bound of Linear Operation.md"
ingested: 2026-06-09
---

Consider the problem
$$
\mathbf{A}(\mathbf{x}+\delta \mathbf{x})=\mathbf{b}+\delta \mathbf{b}
$$
since $\mathbf{b}=\mathbf{Ax}$:
$$
\lVert \mathbf{b} \rVert =\lVert \mathbf{Ax} \rVert \leq \lVert \mathbf{A} \rVert \lVert \mathbf{x} \rVert\to \frac{1}{\lVert \mathbf{x} \rVert }\leq \frac{{\lVert \mathbf{A} \rVert }}{\lVert \mathbf{b} \rVert }
$$
since $\delta \mathbf{x}=\mathbf{A}^{-1}\delta \mathbf{b}$:
$$
\lVert \delta \mathbf{x} \rVert =\lVert \mathbf{A}^{-1}\delta \mathbf{b} \rVert \leq \lVert \mathbf{A}^{-1} \rVert \lVert \delta\mathbf{b} \rVert
$$
combining the inequalities, we have
$$
\frac{{\lVert \delta \mathbf{x} \rVert }}{\lVert \mathbf{x} \rVert }\leq \lVert \mathbf{A} \rVert \lVert \mathbf{A}^{-1} \rVert \frac{{\lVert \delta \mathbf{b} \rVert }}{\lVert \mathbf{b} \rVert }=\kappa(\mathbf{A})\frac{{\lVert \delta \mathbf{b} \rVert }}{\lVert \mathbf{b} \rVert }
$$
which shows how an error in $\mathbf{b}$ can propagate through to the solution of $\mathbf{x}$.

Another relevant scenario is
$$
(\mathbf{A}+\delta \mathbf{A})(\mathbf{x}+\delta \mathbf{x})=\mathbf{b}
$$
which gives the solution
$$
\frac{{\lVert \delta \mathbf{x} \rVert }}{\lVert \mathbf{x}+\delta \mathbf{x}\rVert }\leq \lVert \mathbf{A}^{-1} \rVert \lVert \delta \mathbf{A} \rVert =\kappa(\mathbf{A}) \frac{{\lVert \delta \mathbf{A} \rVert }}{\lVert \mathbf{A} \rVert }
$$
