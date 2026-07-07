---
source: KaedeSync/_Knowledge/Information Theory/Coding/Source Coding/Symbol Coding/Shannon-Fano Coding.md
ingested: 2026-07-06
---

[[Source Coding]]

Since the codeword lengths $\mathcal l_{i}$ are integers, an obvious way to choose them is
$$
l_{i}=\left\lceil  \log_{2} \frac{1}{p_{i}}  \right\rceil
$$
therefore,
$$
L=\sum_{i}p_{i}l_{i}< \sum_{i}p_{i}\left( \log_{2} \frac{1}{p_{i}}+1 \right)=H(X)+1
$$
Construction of Shannon-Fano coding: assign nodes on a binary tree with node depth corresponding to codeword length.