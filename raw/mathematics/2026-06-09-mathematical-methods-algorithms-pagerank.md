---
source: "KaedeSync/_Knowledge/Mathematics/Mathematical Methods/Algorithms/PageRank.md"
ingested: 2026-06-09
---

Fix issues with eigenvector centrality on not-strongly-connected directed graphs by adding teleportation. Assume a random surfer that:
- with probability $\alpha$, follow a random outgoing link
- with probability $1-\alpha$, teleport uniformly

Let $x_{i}$ be the pagerank score of node $i$, i.e. long-term probability that the random surfer is at node $i$:
$$
x_{i}=\alpha \sum_{j}\left( \frac{A_{ji}}{k_{j}} \right)x_{j}+\frac{{1-\alpha}}{n}
$$
The first link movement term sums the probability of moving from another node to this node along all incoming links. $A_{ji} / k_{j}$ denotes the probability that the surfer moves to node $i$ given that it is at node $j$, and $x_{j}$ is the long-term probability that the surfer is at node $i$. The random teleportation can move surfer in from any node indifferently.

Let the random-walk transition matrix $W$ be
$$
W_{ij}=\frac{A_{ji}}{k_{j}}
$$
then we can vectorise the equation:
$$
x=\alpha Wx+\frac{1-\alpha}{n} \mathbf{1}
$$
exact solution:
$$
x=\frac{{1-\alpha}}{n}(I-\alpha W)^{-1}\mathbf{1}
$$
iterative solution:
$$
x^{(t+1)}=\alpha Wx^{(t)}+\frac{{1-\alpha}}{n}\mathbf{1}
$$

[[Graph]]