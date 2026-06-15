---
source: KaedeSync/_Knowledge/Machine Learning/Basics/Theories/Actual Loss.md
ingested: 2026-06-08
---

We build a classifier that predicts estimation $\hat{y}$ for the correct label $y^{*}$ based on known input $\mathbf{x}^{*}$:
$$
f(\mathbf{x}^{*}, \theta)
$$
the classifier has model parameters $\theta$ which needs to be trained to optimise prediction.

Specifically, we train parameters $\theta$ to minimise the expected loss/actual loss $\mathcal L_{act}$:
$$
\mathcal L_{act}=\int\left[\sum_{i=1}^{K}\mathcal L(f(\mathbf{x},\theta),\omega_{i})P(\omega_{i}|\mathbf{x})\right]P(\mathbf{x})d\mathbf{x}
$$
Note that the expected loss is the integration of loss across all possible inputs.

[[Loss Function]]