---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Estimators/Generative Model Estimation.md"
ingested: 2026-06-09
---

[[Estimation and Inference]], and [[Machine Learning]]

Use generative model to approximate $P(\omega|x^{*})$.
Posterior distribution of class $\omega_{i}$ for unseen observation $x^{*}$:
$$
p(w_{i}|x^{*},\theta)=\frac{p(x^{*},\omega_{i},\theta)}{\sum_{j=1}^{K}p(x^{*},\omega_{j},\theta)}= \frac{p(x^{*}|\omega_{i},\theta)P(\omega_{i})}{\sum_{j=1}^{K}p(x^{*}|\omega_{j},\theta)P(\omega_{j})}
$$
where $p(x^{*}|\omega_{i},\theta)$ is a likelihood of the observation given class $\omega_{i}$.

Then, we train different models using maximum likelihood for each class $\omega_i$:
$$
\hat{\theta_{i}}=\arg\max_{\theta}\left\{  \sum_{j:y_{j}=\omega_{i}}\log(p(x_{j}|\omega_{i},\theta))  \right\}
$$
That is, most likely parameter that generated data *of corresponding label*

![[Class Prior Estimation]]