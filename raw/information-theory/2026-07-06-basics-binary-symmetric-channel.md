---
source: KaedeSync/_Knowledge/Information Theory/Basics/Binary Symmetric Channel.md
ingested: 2026-07-06
---

[[Binary Channel]] and [[Discrete Memoryless Channel]]

$$
\begin{align}
P(Y=0|X=0)&=1-p \\
P(Y=0|X=1)&=p \\
P(Y=1|X=0)&=p \\
P(Y=1|X=1)&=1-p
\end{align}
$$
- $p$ is the *crossover probability*; the channel is called $BSC(p)$.
- Key question: how to design a good error-correcting code for BSC?