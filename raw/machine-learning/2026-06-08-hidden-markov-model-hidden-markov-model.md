---
source: KaedeSync/_Knowledge/Machine Learning/Hidden Markov Model/Hidden Markov Model.md
ingested: 2026-06-08
---

In a hidden markov model, we assume:
- there is a sequence of (discrete) hidden states $s$ (unknown).
- there is a sequence of observations $x$ (known).
- The system follows state transition probabilities $P(s_{t}|s_{t-1})$ and emission (observation) probabilities $P(x_{t}|s_{t})$.

Many often, we do not know about the transition or emission probabilities. We build a model to infer the states, and the task is to infer the model parameters.

The likelihood of the data is
$$
p(x_{1},\dots,x_{T})=\sum_{\mathbf{s}\in \mathbf{S}_{T}}p(\mathbf{s})p(x_{1},\dots,x_{T}|\mathbf{s})=\sum_{\mathbf{s} \in \mathbf{S}_{T}}p(s_{0})\prod_{t=1}^{T}P(s_{t}|s_{t-1})p(x_{t}|s_{t})
$$
What are the parameters of the model?
- State transition matrix $\mathbf{A}$
- State output probability $\{ b_{2}(x_{t}),\dots,b_{N-1}(x_{t}) \}$ where
$$
b_{j}(x_{t})=p(x_{t}|s_{t}=j)
$$
is the likelihood of observation $x_{t}$ in state $j$.
- Initial state probability $p(s_{0})$.
