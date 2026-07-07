---
source: KaedeSync/_Knowledge/Information Theory/Coding/Channel Coding/LDPC/Message Passing.md
ingested: 2026-07-06
---

Message passing is a class of iterative algorithms, where in each step: 
1. Each variable node $v$ sends a message to each check node $c$ that it is connected to.
2. Each check node $c$ sends a message to each variable node $v$ that it is connected to. 

These messages are denoted by $\{ m_{vc} \}$ and $\{ m_{cv} \}$ , respectively.

[[Low Density Parity Check Matrix (LDPC)]]