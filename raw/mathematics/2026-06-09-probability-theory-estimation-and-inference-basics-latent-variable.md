---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Basics/Latent Variable.md"
ingested: 2026-06-09
---

A latent variable is a variable that:
- represents (and compresses) the history,
- may be discrete or continuous,
- is marginalised out to obtain the probability of the observed data,
- does not have to have any direct human meaning.

We have a set of observed data $bf=\{ x_{1},\dots,x_{N} \}$. We believe that the data is associated (or generated from) a hidden (latent) variable, $\mathbf{z}$, either discrete or continuous. Therefore, we build the model for data $X$ as:
$$
p(x,z|\theta)
$$
where data and latent variable are jointly distributed, with model parameter $\theta$. 

To evaluate data log-likelihood, we marginalise:
$$
\mathcal{L}(\theta)=\sum_{i=1}^{N}\log p(x_{i}|\theta)=\sum_{i=1}^{N}\sum_{z_{j}}\log p(x_{i},z_{j}|\theta)
$$

[[Machine Learning]]