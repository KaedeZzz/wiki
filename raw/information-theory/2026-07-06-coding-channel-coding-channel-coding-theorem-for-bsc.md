---
source: KaedeSync/_Knowledge/Information Theory/Coding/Channel Coding/Channel Coding Theorem for BSC.md
ingested: 2026-07-06
---

[[Channel Coding Theorem]]
[[Idea of Channel Rate for DMC]]

For [[Binary Symmetric Channel]] with flip probability $f$ (whose capacity is $C=1-\mathcal H_{2}(f)$),
for any $\epsilon>0$ and $R<C$, for sufficiently large $N$, there exists a code of length $N$ and a rate $\geq R$ and a decoder such that the probability of block error is less than $\epsilon$.

For input sequence $X^{n}$, the output is generated as 
$$
Y_{i}=X_{i}\oplus E_{i}
$$
- $E_{1},\dots,E_{n}$ are i.i.d. $\sim Bernoulli(f)$ is the sequence of errors introduced by the channel ($\oplus$ denotes modulo-two addition).
- For large $n$, the number of ones in $(E_{1},\dots,E_{n})\approx 0.1n$ (from [[Asymptotic Equipartition Property (AEP)]])

The size of the set of $Y^{n}$ sequences “typical” with any given input sequence $X^{n}$ is approximately $2^{nH_{2}(f)}$ (from [[Typical Set]]).

Let us **pick a typical set for each possible input message**, such that none of these typical sets are intersecting. The total number of non-intersecting sets we can pick out are:
$$
2^{nR}\approx \frac{2^{n}}{2^{nH_{2}(f)}}\implies R=1-H_{2}(f)
$$