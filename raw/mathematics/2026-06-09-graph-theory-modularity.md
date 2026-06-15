---
source: "KaedeSync/_Knowledge/Mathematics/Graph Theory/Modularity.md"
ingested: 2026-06-09
---

Measures [[Assortativity]] in categorical variables.

Let $g_{i}$ be the category of node $i$, such that $g_{i}=r$ means the node $i$ is in category $r$. Define $\delta_{g_{i},r}$ as an indicator variable, we compute the covariance of this variable across edges:
$$
\frac{1}{2m}\sum_{i,j}A_{ij}\delta_{g_{i},r}\delta_{g_{j},r}-\left( \frac{1}{2m}\sum_{i}k_{i}\delta_{g_{i},r} \right)^{2}
$$
Then, the modularity is the quantity over all groups, each denoted $r$:
$$
Q=\sum_{r}\left(\frac{1}{2m}\sum_{i,j}A_{ij}\delta_{g_{i},r}\delta_{g_{j},r}-\left( \frac{1}{2m}\sum_{i}k_{i}\delta_{g_{i},r} \right)^{2}\right)
$$
Taking sum and re-arranging gives
$$
\begin{align}
Q & =\sum_{r}\left(\frac{1}{2m}\sum_{i,j}A_{ij}\delta_{g_{i},r}\delta_{g_{j},r}-\left( \frac{1}{2m}\sum_{i}k_{i}\delta_{g_{i},r} \right)^{2}\right) \\
 & =\sum_{r}\left( \frac{1}{2m}\sum_{i,j}A_{ij}\delta_{g_{i},r}\delta_{g_{j},r}-\frac{1}{(2m)^{2}}\sum_{i,j}k_{i}k_{j}\delta_{g_{i},r}\delta_{g_{j},r}\right) \\
 & =\sum_{r}\sum_{i,j}\left[\frac{1}{2m}A_{ij}-\frac{1}{(2m)^2}k_i k_j\right]\delta_{g_i,r}\delta_{g_j,r} \\
 & =\sum_{i,j}\left[\frac{1}{2m}A_{ij}-\frac{1}{(2m)^2}k_i k_j\right]\delta_{g_i,g_{j}}
\end{align}
$$
