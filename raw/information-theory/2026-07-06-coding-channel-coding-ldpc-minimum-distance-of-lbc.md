---
source: KaedeSync/_Knowledge/Information Theory/Coding/Channel Coding/LDPC/Minimum Distance of LBC.md
ingested: 2026-07-06
---

[[Linear Block Code]] and [[Minimum Distance of Code]]

The [[Hamming Distance]] between two binary vectors $u,v$ caan be expressed as
$$
d(u,v)=wt(u+v)
$$
where $wt$ refers the Hamming weight of the vector, i.e. the number of ones in it.

For any two codewords $c_{i},c_{j}$ of an LBC, note that $c_{i}+c_{j}$ is also a codeword. Therefore:
$$
d_{\min}=\min_{i\neq j}wt(c_{i}+c_{j})=\min_{c_{k}\neq 0}wt(c_{k})
$$
The minimum distance of an LBC equals the minimum Hamming weight among the non-zero codewords.