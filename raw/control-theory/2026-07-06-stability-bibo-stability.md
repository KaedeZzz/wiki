---
source: KaedeSync/_Knowledge/Control Theory/Stability/BIBO Stability.md
ingested: 2026-07-06
---

[[Control]]

A discrete-time system is stable if [[Bounded Signal]] inputs give bounded outputs.

Strict definition:
for any constant $M$, there exists a constant $N$ such that, ***for any*** input signal bounded by $M$, the output is bounded by $N$.

1. *If a bounded input gives an unbounded output, the system is unstable.*
2. *For some unstable systems, there exists a collection of bounded input signals which each of them gives bounded output but there exists no finite $N$ than can bound all outputs. In other words, there exists a way to generate input signals that is bounded but whose output can exceed **any** finite boundary.*

