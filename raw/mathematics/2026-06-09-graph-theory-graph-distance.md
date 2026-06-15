---
source: "KaedeSync/_Knowledge/Mathematics/Graph Theory/Graph Distance.md"
ingested: 2026-06-09
---

The shortest path between two nodes is the minimum number of edges that would have to be crossed in order to reach one from the other. 

Often this is known as the *distance* because it obey the properties of a distance metric:
$$
\begin{align}
s(i,i) & =0 \\
s(i,j) & =s(j,i) \\
s(i,j)  & \leq s(i,k)+s(k,j)
\end{align}
$$

[[Graph]]