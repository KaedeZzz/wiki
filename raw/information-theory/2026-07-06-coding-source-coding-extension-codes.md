---
source: KaedeSync/_Knowledge/Information Theory/Coding/Source Coding/Extension Codes.md
ingested: 2026-07-06
---

[[Source Coding]]
Given a binary code $C$ for alphabet $\mathcal X$, the extension code $C^{n}$ is the code applied *symbol-to-symbol* to strings in $x^{n} \in \mathcal X^{n}$, that is:
$$
C(x_{1}x_{2}\dots x_{n})=C(x_{1})C(x_{2})\dots C(x_{n})
$$
The extension code is called *uniquely decodable* if for each binary codeword $C^{n}$, there is *only one possible source* string that can produce it.

[[Prefix-free Code]] are uniquely decodable, but not all uniquely decodable codes are prefix-free.