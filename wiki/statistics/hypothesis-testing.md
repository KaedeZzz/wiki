---
summary: 频率派假设检验用决策规则从数据选 H₀/H₁；两种误差（假阳性 α、假阴性 β）不可同时最小化，Neyman-Pearson 引理证明似然比阈值检验在给定 α 下 β 最小；对数似然比在两假设下的极限恰为 ±KL 散度。
tags: [statistics, hypothesis-testing, frequentist]
updated: 2026-07-06
sources:
  - raw/statistics/2026-07-06-hypothesis-testing-hypothesis-testing.md
  - raw/statistics/2026-07-06-hypothesis-testing-decision-rule.md
  - raw/statistics/2026-07-06-hypothesis-testing-error-types.md
  - raw/statistics/2026-07-06-hypothesis-testing-type-i-error.md
  - raw/statistics/2026-07-06-hypothesis-testing-type-ii-error.md
  - raw/statistics/2026-07-06-hypothesis-testing-neyman-pearson-lemma.md
  - raw/statistics/2026-07-06-hypothesis-testing-theorem-of-approximation-of-llr.md
  - raw/statistics/2026-07-06-hypothesis-testing-confidence-interval.md
---

# 假设检验

## 定义

给定观测 $X_1,\dots,X_n$ 以及两个假设

$$H_0: X_i \overset{\text{i.i.d.}}\sim P,\qquad H_1: X_i \overset{\text{i.i.d.}}\sim Q$$

**决策规则** $\delta:\text{数据}\to\{H_0, H_1\}$ 把数据映到二元决策。频率派假设检验的目标是**在 $H_0$ 视为默认的前提下**做出这个决策——若数据在 $H_0$ 下"够罕见"就拒绝 $H_0$。

**统计显著性**：当结果在 $H_0$ 下发生概率极低时称之为显著。**p 值**：在 $H_0$ 为真下观测到"至少同样极端"结果的概率；**显著性水平** $\alpha$（惯用 $0.05$ 或 $0.01$）为拒绝 $H_0$ 的门槛。

## 关键点

### 两类错误

| 真实 $\backslash$ 决策 | 选 $H_0$ | 选 $H_1$ |
|---|---|---|
| **$H_0$ 真** | 正确 | **Type-I 错误**（假阳性），概率 $\alpha$ |
| **$H_1$ 真** | **Type-II 错误**（假阴性），概率 $\beta$ | 正确 |

$1-\beta$ 称为**检验功效**（power）。**$\alpha$ 和 $\beta$ 之间的权衡不可回避**——降低一个通常抬高另一个（需增加样本量 $n$ 才能同时压小两者）。

### Neyman-Pearson 引理

在**简单假设 vs 简单假设**（$P, Q$ 都完全指定）下，**似然比检验**

$$\Lambda(\mathbf{x}) = \frac{\prod_i Q(x_i)}{\prod_i P(x_i)} \gtrless \tau \Rightarrow \text{选 } H_1 \text{ or } H_0$$

在**给定 Type-I 上限 $\alpha$ 时使 Type-II 概率 $\beta$ 最小**——即似然比阈值检验是**最强检验（most powerful test）**。

推论：任何其他检验若 Type-I $\leq \alpha$，则 Type-II $\geq \beta$。所以工程上"我先固定假阳性率再最大化检出率"的直觉严格成立。

### 对数似然比的渐近行为

**归一化 LLR**：

$$\text{LLR}_n = \frac{1}{n}\sum_i \log\frac{Q(X_i)}{P(X_i)}$$

由弱大数定律（见 [[limit-theorems]]）：

- 在 $H_0$（$X_i\sim P$）下：$\text{LLR}_n \to \mathbb{E}_P[\log\tfrac{Q}{P}] = -D_{KL}(P\|Q)$
- 在 $H_1$（$X_i\sim Q$）下：$\text{LLR}_n \to \mathbb{E}_Q[\log\tfrac{Q}{P}] = D_{KL}(Q\|P)$

即**两条真实分布下的 LLR 极限分别是 $\pm$KL 散度**。这直接给出：

- 两假设越"远离"（KL 越大） → 极限分离越大 → 检验越容易
- **Chernoff-Stein 引理**：固定 $\alpha$ 后 $\beta$ 的指数衰减速率为 $D_{KL}(P\|Q)$

这条渐近性质把假设检验与 [[kl-divergence]]、[[typicality-and-aep]] 紧密联系起来——KL 就是两分布"可分辨性"的信息论刻画。

### 置信区间

对样本均值 $X$ 与真值 $\mu$、噪声标准差 $\sigma$，Gaussian 近似下：

$$\Pr(|X-\mu| \leq m\sigma) = 2\Phi(m) - 1$$

由此反推区间：$95\%$ CI 对应 $m\approx 1.96$。置信区间与假设检验对偶——CI 覆盖 $\mu_0$ ⇔ $H_0: \mu=\mu_0$ 在同水平下未被拒绝。

## 关联概念

- [[estimation-theory]] — MLE/MAP 是**参数估计**，假设检验是**判定**；两者在 GLR 检验中融合
- [[kl-divergence]] — LLR 的极限、检验错误率的指数衰减都用 KL 刻画
- [[limit-theorems]] — LLR 收敛来自弱大数定律
- [[typicality-and-aep]] — Neyman-Pearson 界的另一种"典型集"式证明
- [[gaussian-distribution]] — 置信区间的高斯近似基础
- [[monte-carlo-methods]] — 检验统计量分布不可求时用 bootstrap / 置换检验
