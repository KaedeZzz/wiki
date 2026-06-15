---
source: "KaedeSync/_Knowledge/Mathematics/Graph Theory/Betweenness.md"
ingested: 2026-06-09
---

Betweenness measures the structural role a node plays in holding the network together.

Let $s_{jk}$ be the total number of shortest paths between $j$ and $k$, and $s_{jk}(i)$ be the number of shortest paths between $j$ and $k$ that passes node $i$. The betweenness centrality of node $i$ is defined as:
$$
b_{i}=\sum_{j,k} \frac{s_{jk}(i)}{s_{jk}}
$$
