---
summary: PID = 比例 + 积分 + 微分：控制量是误差 e(t) 的当前值、累积和变化率的加权和；Ziegler-Nichols 用临界振荡的周期和增益给出启发式调参。
tags: [control-theory, controller-design]
updated: 2026-07-06
sources:
  - raw/control-theory/2026-07-06-pid-proportional-integral-derivative-controller-(pid).md
  - raw/control-theory/2026-07-06-pid-ziegler-nichols-tuning-rule.md
---

# PID 控制器

## 定义

比例-积分-微分控制器（PID）是工业界最常见的反馈控制器。给定误差 $e(t)=r(t)-y(t)$（参考值减输出），控制量：

$$u(t) = K_p\, e(t) + K_i \int_0^t e(\tau)\,d\tau + K_d\, \frac{de(t)}{dt}$$

在 Laplace 域（见 [[laplace-transform]]）：

$$L(s) = K_p + \frac{K_i}{s} + K_d\, s$$

## 关键点

### 三项的作用与调参直觉

| 增益 | 作用 | 过大 | 过小 |
|---|---|---|---|
| $K_p$（比例） | 对当前误差按比例反应 | 振荡、失稳 | 响应迟钝 |
| $K_i$（积分） | 累积历史误差，消除稳态误差 | 超调、振铃 | 稳态偏差残留 |
| $K_d$（微分） | 预判误差趋势，抑制过冲 | 对噪声极敏感 | 缺乏"预见性" |

工程实践中 $K_d$ 通道常串联低通滤波器以抑制噪声。

### Ziegler-Nichols 调参法则

一种**启发式**调参方法。步骤：

1. 只保留 $K_p$（关闭 $K_i, K_d$），逐步增大 $K_p$ 直到系统出现持续等幅振荡。
2. 记录**临界增益** $K_u$ 与**振荡周期** $T_u$。
3. 按查表规则由 $(K_u, T_u)$ 给出 P / PI / PID 各种控制器的推荐 $K_p, K_i, K_d$。

背后逻辑：临界振荡状态对应 Nyquist 轨迹恰好穿过临界点 $-1/K$（见 [[nyquist-stability]]），$K_u$ 是**增益裕度**的临界值（见 [[frequency-response]]），$T_u$ 是该频率的振荡周期。

## 关联概念

- [[transfer-function]] — PID 的 $L(s)$ 即控制器的传递函数，与被控对象串联后进入闭环
- [[laplace-transform]] — PID 的时域积分/微分对应 $1/s$ 与 $s$
- [[frequency-response]] — Ziegler-Nichols 的 $K_u$ 对应增益裕度临界
- [[nyquist-stability]] — 等幅振荡 ⇔ Nyquist 图与 $-1/K$ 相切
