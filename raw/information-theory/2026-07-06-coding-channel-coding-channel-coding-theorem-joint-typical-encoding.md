---
source: KaedeSync/_Knowledge/Information Theory/Coding/Channel Coding/Channel Coding Theorem/Joint Typical Encoding.md
ingested: 2026-07-06
---

[[Channel Coding]]

The decoder declares that the message $\hat{ W}$ was sent if both the following conditions are satisfied:
1. $(X^{n}(\hat{W}),Y^{n})$ is **[[Jointly Typical]]** with respect to $P_{X}P_{Y|X}$.
2. There exists no other message $W'\neq \hat{W}$ such that $(X^{n}(W'),Y^{n})$ is jointly typical.

If no $\hat{ W}$ is found or more than one is found, an error is declared.