---
source: "KaedeSync/_Knowledge/Mathematics/Graph Theory/Random Graph.md"
ingested: 2026-06-09
---

In the random [[Graph]] $G(n,p)$ we have $n$ nodes, each pair of which is connected with probability $p$. That is,
$$
A_{ij}\sim \text{Bernoulli}(p)
$$
Note that $A_{ij}=A_{ji}$ for undirected graphs, so each edge can only be generated once.

Therefore, the probability of a particular realisation of a random graph:
$$
P(A)=\prod_{i<j}p^{A_{ij}}(1-p)^{1-A_{ij}}
$$
