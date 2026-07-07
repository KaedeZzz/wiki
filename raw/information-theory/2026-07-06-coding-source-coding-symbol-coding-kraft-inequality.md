---
source: KaedeSync/_Knowledge/Information Theory/Coding/Source Coding/Symbol Coding/Kraft Inequality.md
ingested: 2026-07-06
---

[[Source Coding]]
Assume that each binary coding takes a cost of $2^{-l_{i}}$ where $l_{i}$ is the length of the code. Kraft inequality states that:
$$
\text{If a code is uniquely decodable, then }\sum_{i}2^{-l_{i}}\leq 1
$$

Explanation: (for [[Prefix-free Code]]s)
On the tree of binary codeword, assigning each codeword leads to a set of $2^{l_{max}-l}$ unusable leaves.

![[Pasted image 20241104153213.png]]

After a set of assignments, we find:
$$
\sum_{i=1}^{N}2^{l_{max}-l_{i}}\leq 2^{l_{max}}
$$
that is, *the codes on the deepest layer that is unusable (because its prefix is used)* is less than or equal to *total codes on the deepest layer*.
Transformation of the equation yields $\sum_{i}2^{-l_{i}}\leq{1}$.

It is also a *sufficient* condition: if a set of lengths satisfy this condition, we can always construct a [[Prefix-free Code]] with these lengths.