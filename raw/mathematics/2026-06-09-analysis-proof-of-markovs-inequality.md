---
source: "KaedeSync/_Knowledge/Mathematics/Analysis/Proof of Markov's Inequality.md"
ingested: 2026-06-09
---

Let us define indicator function 
$$
1\{ x\geq a \}=\begin{cases}
1\quad \text{if }x\geq a\\
0\quad \text{if }x< a
\end{cases}
$$
Therefore:
$$
\begin{align}
\mathbb{E}[X]=\sum_{x\geq 0}xP(X=x)&\geq \sum_{x\geq 0}a 1\{ x\geq a \}P(X=x)  \\
&= a\sum_{x\geq 0}1\{ x\geq a \}P(X=x) \\
&\geq a\sum_{x\geq a}P(X=x) \\
&\geq aP(X\geq a)
\end{align}
$$

[[Markov's Inequality]]