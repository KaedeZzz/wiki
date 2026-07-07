---
source: KaedeSync/_Knowledge/Information Theory/Basics/Channel Coding Theorem.md
ingested: 2026-07-06
---

[[Channel Coding]]

**For a [[Discrete Memoryless Channel]] with capacity $\mathcal C$, all rates less than $\mathcal C$ is achievable.**

Specifically,
1. Fix $R<\mathcal C$ and pick any $\epsilon>0$. Then, for *all sufficiently large* $n$, there exists a [[length-n Code]] of rate $R$ with [[Maximal Probability of Error of Code]] less than $\epsilon$.
2. Conversely, any sequence of length-n codes of rate $R$ with Maximal/[[Average Probability of Error of Code]] $P_{e}^{(n)}\to 0$ as $n\to \infty$ must have $R\leq\mathcal C$.
