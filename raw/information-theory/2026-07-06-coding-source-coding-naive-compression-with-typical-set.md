---
source: KaedeSync/_Knowledge/Information Theory/Coding/Source Coding/Naive Compression with Typical Set.md
ingested: 2026-07-06
---

[[Source Coding]]
Let $X^{n}$ be i.i.d. $\sim P$. For any fixed $\epsilon>0$, for $n \in \mathbb{N}^{+}$ sufficiently large, there exists a code that maps sequences $x^{n}$ into binary strings such that the mapping is *one-to-one* and the [[Expected Code Length]] per symbol:
$$
\mathbb{E}\left\{ \frac{1}{n}\mathcal l(X^{n}) \right\}\leq H(X)+\epsilon
$$
###### Explanation
There are at most $2^{n(H(X)+\epsilon)}$ $\epsilon$-typical sequences. 
- We can index each sequence in $A_{\epsilon,n}$ using $\lceil \log 2^{n(H(X)+\epsilon)} \rceil$ bits, and prefix each of these by a flag bit $0$. Then, bits per typical sequence:
$$
\lceil n(H(X)+\epsilon) \rceil +1\leq n(H(X)+\epsilon)+2
$$
- Then, we index each sequence not in the [[Typical Set]] using $\lceil n\log|\mathcal X| \rceil$ bits, and prefix each of these by a flag bit $1$. Then, bits per non-typical sequence:
$$
\lceil n\log|\mathcal X| \rceil +1\leq n\log|\mathcal X|+2
$$
- The purpose of adding a prefix is to make each code unique and *not a prefix of another*.

[[Expected Code Length]]:
$$
\begin{align}
&\mathbb{E}\{\mathcal l(X^{n})\}\\&\leq \sum_{x^{n} \in A_{\epsilon,n}}P(x^{n})(n(H(X)+\epsilon)+2)+\sum_{x^{n} \notin A_{\epsilon,n}}P(x^{n})(n\log|\mathcal X|+2) \\
&\leq 1\cdot n(H(X)+\epsilon)+\epsilon \cdot n\log|\mathcal X|+2 \\
&=n(H(X)+\epsilon)+\epsilon n\log|\mathcal X|+2 \\
&=n(H(X)+\epsilon') \\
&\text{where }\epsilon'=\epsilon+\epsilon \log|X|+\frac{2}{n}.
\end{align}
$$
Note:
- $1$ in row 3 indicates that, at most, *(nearly) all* sequences are in the typical set.
- $\epsilon$ in row 3 means that the probability of a sequence *not* in the typical set is at most $\epsilon$ for some $n$.
Therefore, by picking a small enough $\epsilon$ and then sufficiently large $n$, $\epsilon'$ can be arbitrarily small, making expected codeword length approximate to $nH(X)$.