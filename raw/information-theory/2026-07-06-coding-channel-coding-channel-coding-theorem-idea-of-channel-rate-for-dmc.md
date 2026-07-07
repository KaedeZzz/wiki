---
source: KaedeSync/_Knowledge/Information Theory/Coding/Channel Coding/Channel Coding Theorem/Idea of Channel Rate for DMC.md
ingested: 2026-07-06
---

[[Channel Coding Theorem]]

Fix an input $P_{X}$; together with channel $P_{Y|X}$ the joint distribution is given.

- The total size of all typical sequences is roughly $2^{nH(Y)}$.
- For some input sequence $X^{n}(j)$, the size of typical sequences given $X$ is $2^{nH(Y|X)}$.
- Channel capacity:
$$
2^{nR}\approx\frac{2^{nH(Y)}}{2^{nH(Y|X)}}\implies R\approx H(Y)-H(Y|X)=I(X;Y)
$$
