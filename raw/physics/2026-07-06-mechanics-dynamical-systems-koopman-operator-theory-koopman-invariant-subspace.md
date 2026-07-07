---
source: KaedeSync/_Knowledge/Physics/Mechanics/Dynamical Systems/Koopman Operator Theory/Koopman-invariant Subspace.md
ingested: 2026-07-06
---

A Koopman-invariant subspace is defined as the span of a set of functions $\{ g_{1},g_{2},\dots,g_{p} \}$ if all functions in this subspace
$$
g=\alpha_{1}g_{1}+\alpha_{2}g_{2}+\dots+\alpha_{p}g_{p}
$$
remain in this subspace after being acted on by the Koopman operator $\mathcal K$:
$$
\mathcal Kg=\beta_{1}g_{1}+\beta_{2}g_{2}+\dots+\beta_{p}g_{p}
$$
Therefore it is possible to obtain a finite-dimensional matrix representation of the Koopman operator by restricting it to an invariant subspace spanned by a **finite** number of functions $\{ g_{j} \}_{j=0}^{p}$.

Any finite set of eigenfunctions of the Koopman operator will span an invariant subspace; discovering these eigenfunction coordinates is, therefore, a central challenge, as they provide intrinsic coordinates along which the dynamics behave **linearly**.

In practice, it is more likely that we will identify an *approximately* invariant subspace where each of the functions.

![[Intrinsic Coordinates of Koopman-Invariant Subspace]]