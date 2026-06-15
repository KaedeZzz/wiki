---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Estimators/Class Prior Estimation.md"
ingested: 2026-06-09
---

Generative classifier requires estimate of class prior $P(\omega_{i})$
Simple approach: count
$$
P(\omega_{i})=\frac{1}{N}\sum_{j:y_{j}=\omega_{i}}1
$$
To amend cases where no case present, often used in [[Naive Bayes]]:
$$
P(\omega_{i})\approx \frac{1}{N+K}\left(1+\sum_{j:y_{j}=\omega_{i}}1\right)
$$
