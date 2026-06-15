---
source: KaedeSync/_Knowledge/Machine Learning/Physics Informed ML/Sparse Identification of Nonlinear Dynamics (SINDy).md
ingested: 2026-06-08
---


From data, discover [[Mechanics and Dynamics]]
Important: equations, not black box!

Context: there is a need for interpretable and generalizable machine learning.

![[Principle of Parsimony]]

Model:
$$
\mathbf{\dot{X}}=\mathbf{\Theta}(\mathbf{X})\mathbf{\Xi}
$$

![[Pasted image 20241027114308.png]]

Objective: find as few terms in $\mathbf{\Theta}(\mathbf{X})$ to describe the dynamics.

![[PySINDy]]