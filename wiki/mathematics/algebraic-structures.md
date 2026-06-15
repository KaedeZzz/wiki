---
summary: 从半群到域，代数结构按运算丰富程度构成层级：半群 → 幺半群 → 群 → 阿贝尔群 → 环 → 域。
tags: [mathematics, algebra]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-algebra-groups.md
  - raw/mathematics/2026-06-09-algebra-rings-fields.md
  - raw/mathematics/2026-06-09-algebra-fundamentals.md
---
# 代数结构

## 定义

代数结构是一个集合 $S$ 配上一个或多个二元运算，满足特定公理。随着公理增多，结构依次增强：

| 结构 | 要求 |
|------|------|
| 半群 (Semigroup) | $(S, \cdot)$，$\cdot$ 满足结合律 |
| 幺半群 (Monoid) | 半群 + 存在单位元 $e$：$e \cdot a = a \cdot e = a$ |
| 群 (Group) | 幺半群 + 每个元素有逆元：$a \cdot a^{-1} = e$ |
| 阿贝尔群 (Abelian Group) | 群 + 运算满足交换律：$a \cdot b = b \cdot a$ |
| 环 (Ring) | $(R, +, \times)$：加法构成阿贝尔群，乘法构成幺半群，且乘法对加法满足分配律 |
| 域 (Field) | 环 + 非零元素关于乘法也构成阿贝尔群 |

## 关键点

- **结合律**是最基础的约束：$(a \cdot b) \cdot c = a \cdot (b \cdot c)$。
- **群**是代数学的核心对象。拉格朗日定理：有限群中子群的阶整除群的阶。
- **环**有两个运算，加法"好"（阿贝尔群），乘法"弱"（可能无逆元、不交换）。
- **域**是"最好的"代数结构：加减乘除都可做。典型例子：$\mathbb{Q}, \mathbb{R}, \mathbb{C}, \mathbb{F}_p$（$p$ 为素数）。
- **同态** (homomorphism)：保持运算结构的映射；**同构** (isomorphism)：双射同态。

## 关联概念

- [[number-theory]] — 整数环 $\mathbb{Z}$ 是环论的原型；模运算构成 $\mathbb{Z}/n\mathbb{Z}$，当 $n$ 为素数时为域。
