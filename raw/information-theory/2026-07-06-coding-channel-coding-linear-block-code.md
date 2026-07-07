---
source: KaedeSync/_Knowledge/Information Theory/Coding/Channel Coding/Linear Block Code.md
ingested: 2026-07-06
---

What is linearity? #TBD 
A $(n,k)$ *linear* block code is defined in terms of $k$ length-$n$ binary vectors $\underline{g}_{1},\dots,\underline{g}_{k}$. A sequence of $k$ data bits $\underline{x}=(x_{1},\dots,x_{k})$ is mapped to a length-$n$ codeword $\underline{c}$ by:
$$
\underline{c}=x_{1}\underline{g}_{1}+\dots+x_{k}\underline{g}_{k}
$$
which can be compactly written as (row vectors)
$$
\underline{c}=\underline{x}G\text{, where }G=
\begin{bmatrix}
\underline{g}_{1} \\
\vdots \\
\underline{g}_{k}
\end{bmatrix}
$$
- $G$ is known as a **generator** **matrix**
- $k$ is called the code dimension, $n$ is the block length
- The matrix multiplication is over the *binary field*:

![[Binary Field Arithmetics]]

