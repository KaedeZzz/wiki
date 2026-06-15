---
source: "KaedeSync/_Knowledge/Mathematics/Graph Theory/Configuration Model.md"
ingested: 2026-06-09
---

Given a target degree distribution $p_{k}$, generate a random graph with (approximately) that degree distribution:
- For each node $i=0,\dots,n-1$, sample a degree $k_{i}\sim p_{k}$.
- Give node $i$ exactly $k_{i}$ half-edges.
- Pair half-edges uniformly at random to form edges.

This produces a [[Multi-Graph]] where self-loops and multi-edges exist, but those occur with vanishing probability as $n\to \infty$.

[[Graph]]