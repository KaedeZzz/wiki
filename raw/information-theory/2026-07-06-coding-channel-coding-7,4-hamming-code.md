---
source: KaedeSync/_Knowledge/Information Theory/Coding/Channel Coding/7,4 Hamming Code.md
ingested: 2026-07-06
---

[[Channel Coding]]
Take 4 source bits and encode into 7 transmitted bits.
$$
\begin{aligned}
t_{5}=s_{1}\oplus s_{2} \oplus s_{3} \\
t_{6}=s_{2}\oplus s_{3} \oplus s_{4} \\
t_{7}=s_{1}\oplus s_{3} \oplus s_{4} \\
\end{aligned}
$$
Any single flip can be detected, but more than 1 flip makes guess different from source.

