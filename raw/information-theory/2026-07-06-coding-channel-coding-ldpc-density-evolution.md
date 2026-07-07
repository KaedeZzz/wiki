---
source: KaedeSync/_Knowledge/Information Theory/Coding/Channel Coding/LDPC/Density Evolution.md
ingested: 2026-07-06
---

#SUPO Predicts performance of infinite length code. Shows asymptote/limit.
Density evolution is a technique to predict the decoding performance of codes with a given $\lambda(x),\rho(x)$ and large $n$.

*Key assumption: incoming messages at each node are independent (which is rarely true)*

First consider regular LDPC codes.
- Let $p_{t}$ be the probability that an outgoing $v \to c$ message (along an edge picked uniformly at random) is an erasure (“?”) in step t. On a BEC with erasure probability $\epsilon$, we have $p_{0}=\epsilon$.
- Let $q_{t}$ be the probability that an outgoing $c \to v$ message is a “?” in step t. We have $q_{0}=1$ as all first $m_{cv}$ are erasures.

For $t\geq 1$, assuming all the incoming messages at each variable/check node are independent, we have:
- The probability that the variable AND all the $d_{v}-1$ incoming messages being erased is:
$$
p_{t}=\epsilon(q_{t-1})^{d_{v}-1}
$$
- The probability that AT LEAST ONE of the $d_{c}-1$ incoming messages is erased is:
$$
q_{t}=1-(1-p_{t})^{d_{c}-1}
$$
- Combined:
$$
p_{t}=\epsilon(1-(1-p_{t})^{d_{c}-1})^{d_{v}-1}
$$
The density evolution **recursion** predicts the fraction $\epsilon$ of erased bits at the end of each step $t$.

![[Shannon Limit of BEC]]

[[Message Passing for Decoding Binary Erasure Channel]], [[Degree Distribution]]