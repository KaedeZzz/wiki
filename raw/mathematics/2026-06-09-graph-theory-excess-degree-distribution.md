---
source: "KaedeSync/_Knowledge/Mathematics/Graph Theory/Excess Degree Distribution.md"
ingested: 2026-06-09
---

If we randomly pick an edge, and follow it to one of its endpoints, the node will have at least one edge and an excess of $k$ further edges. We end up at a node of degree $k+1$ with probability $q_{k}$. 

The distribution relates to node degree distribution in a way where:
$$
q_{k}=\frac{{(k+1)p_{k+1}}}{E[k]}
$$
generation function relationship: define [[Generation Function]] be
$$
g(z)=\sum_{k=0}^{\infty}z^{k}p_{k}
$$
then
$$
g'(1)=\sum_{k=1}^{\infty}kp_{k}=E[k]
$$
and the ratio is the generation function of $q$:
$$
\frac{g'(z)}{g'(1)}=\sum_{k=0}^{\infty} \frac{z^{k}{(k+1)p_{k+1}}}{E[k]}=\sum_{k=0}^{\infty}z^{k}q_{k}
$$
