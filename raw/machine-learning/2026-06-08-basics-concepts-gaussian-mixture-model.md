---
source: KaedeSync/_Knowledge/Machine Learning/Basics/Concepts/Gaussian Mixture Model.md
ingested: 2026-06-08
---

Define $\mathbf{x}$ the observation, $c_{m}$ is the [[Latent Variable]] of the component that the observed data comes from. Each component is modelled using a Gaussian distribution.
$$
p(\mathbf{x})=\sum_{m=1}^{M}p(c_{m})p(\mathbf{x}|c_{m})=\sum_{m=1}^{M}\pi_{m}\mathcal{N}(\mathbf{x};\mu_{m},\mathbf{\Sigma}_{m})
$$
where:
- $c_{m}$ is the hidden component label
- $p(c_{m})=\pi_{m}$ is the component prior
- $p(\mathbf{x}|c_{m})$ is the Gaussian for component $m$,
- $\theta=\{ \pi_{k},\mu_{k},\mathbf{\Sigma}_{k} \}_{k=1}^{N}$ are all the parameters of this model.

Interpretation:
- each data point comes from one of several hidden Gaussian sources, but we do not know which one.