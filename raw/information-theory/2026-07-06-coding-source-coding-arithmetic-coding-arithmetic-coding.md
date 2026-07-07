---
source: KaedeSync/_Knowledge/Information Theory/Coding/Source Coding/Arithmetic Coding/Arithmetic Coding.md
ingested: 2026-07-06
---

[[Source Coding]]
Key idea: each symbol can be represented as an interval inside $[0,1]$, with length of the interval equal to the symbol probability.

A source with $m$ symbols with probabilities $\{ p_{1},\dots,p_{m} \}$ is represented using the $m$ intervals
$$
\left\{  [\sum_{i=1}^{k-1}p_{i},\sum_{i=1}^{k-1}p_{i}+p_{k})  \right\}_{k=1,\dots,m}
$$
In general, the binary codeword for a symbol with probability $p$ represented by the interval $[a,a+p)$ can be obtained as follows:
1. Find the largest *dyadic* interval of the form $\left[ \frac{j}{2^{l}},\frac{j+1}{2^{l}} \right)$
2. Take the binary representation of the lower end-point of the dyadic interval as the codeword. (This will be the integer $j$ converted to binary and represented using $l$ bits.)

###### Code Length
The dyadic interval has to be contained with an interval of length $p$. Hence
$$
2^{-l}\leq p\implies \left\lceil  \log_{2}\left( \frac{1}{p} \right)  \right\rceil \leq l
$$
However, sometimes we need $\lceil  \log_{2}\left( \frac{1}{p} \right)\rceil+1$ bits
Therefore,
$$
L=\sum_{i}p_{i}\left( 1+\left\lceil  \log_{2}\left( \frac{1}{p_{i}} \right)  \right\rceil  \right)<H(X)+2
$$
Note that arithmetic codes are [[Prefix-free Code]], for that any prefix of a code must indicate a interval that encloses the interval of that code and such overlapping of interval is invalid.

How to encode a sequence? Split the interval once for each symbol; the interval of the sequence with a symbol added is a *sub-interval* of the interval of original sequence.

[[Expected Code Length]] for length $n$ sequence:
$$
L_{n}=\sum_{x^{n}}p(x^{n})l(x^{n})<\sum_{x^{n}}p(x^{n})\left( \log_{2} \frac{1}{p(x_{1},\dots,x_{n})}+2 \right)=H(X^{n})+2
$$
Therefore the [[Expected Code Length]] per symbol is:
$$
\frac{L_{n}}{n}< \frac{H(X^{n})}{n}+\frac{2}{n}=H(X)+\frac{2}{n}
$$
Arithmetic coding can achieve expected code length that is **arbitrarily close** to the source entropy!

In the practice of the algorithm, storing upper and lower bounds of the interval may require large number of decimals, rising a precision issue.

Summary:
- Can achieve compression rates very close to the source entropy, with complexity scaling *linearly* with sequence length
- Does require knowledge of conditional distributions of the source
- Assumed distribution of the source does not need to be the real  one
