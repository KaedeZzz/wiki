---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Bayesian Decision Rule.md"
ingested: 2026-06-09
---

**Optimal estimation** (of label) **minimises expected [[Loss Function]]**:
$$
\hat{ \omega}=\arg\min_{\omega}\left\{  \sum_{i=1}^{K}\mathcal L(\omega,\omega_{i})P(\omega_{i}| x^{*}) \right\}
$$
where $x^{*}$ is the input, $\omega$ is the decision and $\omega_{i}$ are correct labels.
But, we do not know the true probability $P(\omega_{i}\text|x^{*})$; we train a **model** $P(\omega|x^{*},\theta)$ that approximates it. Training data is used to estimate the model parameters $\theta$.