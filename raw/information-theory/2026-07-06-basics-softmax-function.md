---
source: KaedeSync/_Knowledge/Information Theory/Basics/Softmax Function.md
ingested: 2026-07-06
---

The probability that a data point $(x_{n},y_{n})$ being labelled as category $k$ is:
$$
p(y_{n}=k|\mathbf{w}_{1},\dots,\mathbf{w}_{K},\tilde{\mathbf{x}})=\frac{\exp(\mathbf{w}_{k}^{T}\tilde{\mathbf{x}})}{\sum_{k'=1}^{K}\exp(\mathbf{w}_{k'}^{T}\tilde{\mathbf{x}})}
$$

[[Information Theory]]