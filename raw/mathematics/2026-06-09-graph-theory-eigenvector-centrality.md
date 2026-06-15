---
source: "KaedeSync/_Knowledge/Mathematics/Graph Theory/Eigenvector Centrality.md"
ingested: 2026-06-09
---

A node in a [[Graph]] is **important** if it connects to many other important nodes. 

Denote the importance of node $i$ by $x_{i}$ and a parameter $\alpha$, we have:
$$
x_{i}=\alpha \sum_{j}A_{ij}x_{j}
$$
vectorise the equation over all nodes:
$$
\mathbf{x}=\alpha \mathbf{Ax}
$$
which is an eigenvalue problem. 

![[Perron-Frobenius Theorem]]

As a result of this theorem, the solution to the eigenvalue problem is unique, where the largest eigenvalue is taken and the corresponding eigenvector is the solution to the problem.