---
source: "KaedeSync/_Knowledge/Mathematics/Measure Theory/Measure.md"
ingested: 2026-06-09
---

Consider a set of objects $X$. 
A set (of sets) $\Sigma$ is generated from original set of objects $X$ which contains the set $X$, the empty set, and other subsets of $X$, and is [[Closed]] under **countable** complementation, union, and intersections.

A measure $\mu$ is a function from sets to $\mathbb{R}$:
- for all sets $E \in \Sigma$, $\mu(E)\geq0$
- $\mu(\emptyset)=0$
- if $E_{i}\subseteq E_{j},\mu(E_{i})\leq\mu(E_{j})$
- The measure assigned to the (countable) union of disjoint sets in $\Sigma$ is the sum of measures of each set:
$$
\mu(\cup_{k=1}^{\infty}E_{k})=\sum_{k=1}^{\infty}\mu(E_{k})
$$

We say that $\{ X,\Sigma \}$ defines a Measurable Set, and $\{ X,\Sigma,\mu \}$ defines a Measure Space.

[[Mathematics]]