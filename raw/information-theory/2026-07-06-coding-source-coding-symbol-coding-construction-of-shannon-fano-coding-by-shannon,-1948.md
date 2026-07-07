---
source: KaedeSync/_Knowledge/Information Theory/Coding/Source Coding/Symbol Coding/Construction of Shannon-Fano Coding by Shannon, 1948.md
ingested: 2026-07-06
---

#ESSENTIAL 
[[Shannon-Fano Coding]]
Procedure:
- Arrange the messages of length $N$ in order of decreasing probability and suppose their probabilities are $p_{1},p_{2},p_{3},\dots,p_{n}$. 
- Let $P_{s}=\sum_{i=1}^{s-1}p_{i}$; that is, $P_{s}$ is the cumulative probability up to, but not including, $p_{s}$. 
- We first encode into a binary system. The binary code for message $s$ is obtained by expanding $P_{s}$ as a binary number. The expansion is carried out to $m_{s}$ places, where $m_{s}$ is the integer satisfying
$$
\log_{2} \frac{1}{p_{s}}\leq m_{s} < 1+\log_{2} \frac{1}{p_{s}}
$$
That is,
$$
m_{s}=\left\lceil  \log_{2} \frac{1}{p_{s}}  \right\rceil 
$$
Thus the messages of high probability are represented by short codes and those of low probability by long codes. From these inequalities we have:
$$
\frac{1}{2^{m_{s}}}\leq p_{s} < \frac{1}{2^{m_{s}-1}}
$$
Since $p_{s}\geq \frac{1}{2^{m_{s}}}$, the remaining codes after will have probability at least $\frac{1}{2^{m_{s}}}$ larger, thus different in the first $m_{s}$ places (at least at the $m_{s}$-th place). 
*For example, if $p_{s}=\frac{1}{16}$, the code $s-1$ and code $s$ may be something like:*
$$
0.0011\dots\to 0.0100\dots
$$
*which is different before or at $m_{s}=4$.*
Consequently, all the codes are different and it is possible to recover message from the code.