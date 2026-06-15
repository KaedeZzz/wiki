---
source: "KaedeSync/_Knowledge/Mathematics/Graph Theory/Assortativity Coefficient.md"
ingested: 2026-06-09
---

 Suppose $x_{i}$ is some numerical property of a node, then, the covariance across edges is:
$$
\frac{1}{2m}\sum_{i,j}A_{ij}x_{i}x_{j}-\left( \frac{1}{2m}\sum_{i,j}A_{ij}x_{i} \right)^{2}=\frac{1}{2m}\sum_{i,j}A_{ij}x_{i}x_{j}-\left( \frac{1}{2m}\sum_{i}k_{i}x_{i} \right)^{2}
$$
and the assortativity score is the normalised covariance, i.e. Pearson [[Correlation]]:
$$
\begin{align}
r & =\frac{{\frac{1}{2m}\sum_{i,j}A_{ij}x_{i}x_{j}-\left( \frac{1}{2m}\sum_{i,j}A_{ij}x_{i} \right)^{2}}}{\frac{1}{2m}\sum_{i,j}A_{ij}x_{i}^{2}-\left( \frac{1}{2m}\sum_{i,j}A_{ij}x_{i} \right)^{2}} \\
 & =\frac{{\frac{1}{2m}\sum_{i,j}A_{ij}x_{i}x_{j}-\left( \frac{1}{2m}\sum_{i}k_{i}x_{i} \right)^{2}}}{\frac{1}{2m}\sum_{i}k_ix_{i}^{2}-\left( \frac{1}{2m}\sum_{i}k_{i}x_{i} \right)^{2}}
\end{align}
$$
Interpretation: 
- $r>0$ indicates assortative mixing where similar nodes connects to similar nodes.
- If $r=1$, then $x_{i}=x_{j}$ across all edges.
- If $r=-1$, then $x_{i}=-x_{j}$ across all edges.

[[Assortativity]]
