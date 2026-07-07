---
source: KaedeSync/_Knowledge/Information Theory/Coding/Channel Coding/Repetition Coding.md
ingested: 2026-07-06
---

[[Channel Coding]]
Repeat each bit $m$ times, denoted as $\mathcal R_{m}$.
$$
\begin{aligned}
\mathcal R_{3}:\\
&s &t \\
&0 \to &000 \\
&1 \to &111
\end{aligned}

$$
Let us denote noise vector to be
$$
n=\begin{cases}
0 \quad\text{if no flipping occurs} \\
1 \quad\text{if flipping occurs}
\end{cases}
$$
Therefore:
$$
r=t \oplus n 
$$
where $\oplus$ denotes modulo 2
How to design decoder $r\to \hat{s}$ ? $\implies$ Best of N (Majority vote decoder).

Data rate: $\frac{1}{m}$
Probability of decoding error follows binomial distribution.

