---
source: KaedeSync/_Knowledge/Communications/State-Space Models/State-space Model.md
ingested: 2026-07-08
---

State of a system is represented as a vector $x_{t} \in \mathbb{R}^{N}\text{ for }t=0, 1,\dots,T$. The update of states are in Markov structure, i.e.:
$$
x_{t+1}\sim f(x_{t+1}|x_{t})
$$
known as **State evolution density**. Specifically, we assume a [[Markov Process]] structure where probability of next state only depends on the last state.

The states are "partially" observed through a likelihood function for observations $\{ y_{t} \}$ which are assumed to depend only on the current state:
$$
y_{t+1}\sim g(y_{t+1}|x_{t+1})
$$
