---
source: KaedeSync/_Knowledge/Communications/Discrete/z-Transform and DTFT/Region of Convergence of z-Transform.md
ingested: 2026-07-08
---

Region where convergent [[z-Transform]] expressions are valid.

In strict terms, when we define a z-Transform, we not only define its expression, but also its region of convergence.

$$
\text{signal}\{ u_{0},u_{1},u_{2},\dots \}\leftrightarrow (\text{expression }U(z),\text{ a region of convergence})
$$

However, in real applications, the region of convergence is often ignored. Why?

![[Analytical Continuation]]

It is ignored when one-sided z-transform is being considered. One-sided z-transform guarantees unique sequence for each z-transform.
*(The editor cannot understand this for now.)* #TBD

However for [[Two-sided z-Transform]], ROC is used to distinguish different signals of same z-transforms and thus cannot be ignored.