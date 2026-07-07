---
source: KaedeSync/_Knowledge/Information Theory/Coding/Source Coding/Symbol Coding/Comparison of Shannon-Fano Coding and Arithmetic Coding.md
ingested: 2026-07-06
---

#ESSENTIAL 
[[Shannon-Fano Coding]], in a way of construction proposed by Claude Shannon in his 1948 paper (See [[Construction of Shannon-Fano Coding by Shannon, 1948]]), is different with [[Arithmetic Coding]] in the following way:

- Shannon-Fano coding saves an extra bit, but it requires sorting the probabilities in decreasing order before coding, which is impractical for long sequences.
- Arithmetic coding may cost an additional bit (when two dyadic intervals coexist), but it does not require any pre-sort.
