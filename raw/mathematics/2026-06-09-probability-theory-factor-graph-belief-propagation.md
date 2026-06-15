---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Factor Graph/Belief Propagation.md"
ingested: 2026-06-09
---

A [[Message Passing]] algorithm.
Messages are passed such that:
- From variable to factor:
$$
m_{i\to a}(x_{i})=\prod_{b \in N(i)\textbackslash a}m_{b\to i}(x_{i})
$$
the message a variable node $i$ sends to factor $a$ is just the product of all incoming messages to $i$ from other neighbouring factors $b$, i.e. everything $i$ “knows” except from $a$.
- From factor to variable:
$$
m_{a\to i}(x_{i})=\sum_{x_{N(a)\backslash i}}\left[f_{a}(x_{N(a)})\prod_{j \in N(a)\backslash i}m_{j\to a}(x_{j})\right]
$$
where $x_{N(a)\backslash i}$ represents all variable neighbours of the factor node $a$ except $x_{i}$.
The factor node $a$ computes how it weights each possible value of $x_{i}$ by:
	- taking the factor potential $f_{a}(x_{N(a)})$ that couples all its variables.
	- multiply by the incoming messages $m_{j\to a}(x_{j})$ from other variables $j$ in the factor (those messages summarize beliefs about those variables from the rest of the graph).
	- summing (marginalising) over all assignments of the other variables $x_{N(a)\backslash i}$ to produce a function of $x_{i}$ only.

- Belief (marginal):
$$
b_{i}(x_{i})\propto \prod_{a \in N(i)}m_{a\to i}(x_{i})
$$
