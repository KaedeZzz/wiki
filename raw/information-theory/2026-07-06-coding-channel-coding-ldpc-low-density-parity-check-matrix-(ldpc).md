---
source: KaedeSync/_Knowledge/Information Theory/Coding/Channel Coding/LDPC/Low Density Parity Check Matrix (LDPC).md
ingested: 2026-07-06
---

Firstly for binary erasure channels.

Iterative decoding: for a message with 1s, 0s, and unknowns, we make ourself lucky by being able to solve for unknowns directly before decoding. To increase chance of success for this, there should be less 1s in the parity check matrix.

In a regular $(n,k)$ LDPC code:
- Each of the $n$ codeword bits is involved in $d_{v}$ parity check equations ('v' stands for variable)
- Each of the $n-k$ parity check equations involves $d_{c}$ code bits. ('c' stands for check)

The **design rate** of a regular LDPC code is $\frac{k}{n}= 1 - \frac{d_{v}}{d_{c}}$
The design rate is the true code rate if the rows of the parity check matrix are linearly independent. Otherwise there exists redundant rows, removing which will result in higher true rate.

[[Linear Block Code]]