---
source: KaedeSync/_Knowledge/Machine Learning/Hidden Markov Model/HMM Forward Algorithm.md
ingested: 2026-06-08
---

Define the forward variable
$$
\alpha_{j}(t)=\log p(x_{1},\dots,x_{t},q_{t}=s_{j})
$$
which is the total probability of all paths arriving at $s_{j}$ at time $t$. It is the log probability of two things happening together:
- we have observed the prefix $x_{1},\dots,x_{t}$, and
- at time $t$, the hidden state is $s_{j}$.

We use [[Dynamic Programming]]/recursion to calculate the probabilities.
At time $t=0$:
$$
\alpha_{1}(i)=p(x_{0}, s_{0}=i)=p(s_{0}=i)p(x_{0}|s_{0}=i)=\pi_{i}b_{i}(x_{0})
$$
Induction for $t\geq 1$: consider a marginalisation along all hidden states
$$
\begin{align}
\alpha_{t}(j) & =\sum_{i=1}^{N}p(\mathbf{x}_{t},s_{t-1}=i,s_{t}=j) \\
 & =\sum_{i=1}^{N}p(\mathbf{x}_{t-1},s_{t-1}=i|\theta)p(s_{t}=j|s_{t-1}=i)p(x_{t}|s_{t}=j) \\
 & =\sum_{i=1}^{N}\alpha_{t-1}(i)A_{ij}b_{j}(x_{t})
\end{align}
$$
Idea: any path that ends in state $s_{j}$ at time $t$ must have come from some previous state $s_{k}$ at time $t-1$, then transitioned from $s_{k}$ to $s_{j}$, then emitted $x_{t}$. Therefore, we sum the earlier path probabilities multiplied by transition and emission probabilities.

Finally, the total likelihood is
$$
p(\mathbf{x_{T}|\theta})=\sum_{i=1}^{N}\alpha_{T}(i)
$$
