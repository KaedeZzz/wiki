---
summary: 整数的整除性、素数、模运算及相关定理（欧几里得算法、欧拉定理、中国剩余定理、Bézout 等式）。
tags: [mathematics, algebra]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-algebra-number-theory.md
  - raw/mathematics/2026-06-09-algebra-fundamentals.md
  - raw/mathematics/2026-06-09-algebra-modular.md
---
# 数论

## 定义

数论研究整数的性质，核心围绕整除性与素数展开。模运算 (modular arithmetic) 是数论的基本工具。

## 关键点

### 最大公约数与欧几里得算法

- **最大公约数**：$\gcd(a, b)$ 是同时整除 $a$ 和 $b$ 的最大正整数。
- **欧几里得算法**：反复取余——$\gcd(a, b) = \gcd(b, a \bmod b)$，直到余数为 0。时间复杂度 $O(\log \min(a,b))$。

### Bézout 等式

对任意整数 $a, b$，存在整数 $x, y$ 使得：

$$ax + by = \gcd(a, b)$$

扩展欧几里得算法可同时求出 $\gcd$ 和系数 $x, y$。

### 欧拉定理与费马小定理

- **欧拉函数**：$\phi(n)$ 为 $1$ 到 $n$ 中与 $n$ 互素的整数个数。
- **欧拉定理**：若 $\gcd(a, n) = 1$，则 $a^{\phi(n)} \equiv 1 \pmod{n}$。
- **费马小定理**（特例）：$p$ 为素数时，$a^{p-1} \equiv 1 \pmod{p}$。

### 中国剩余定理 (CRT)

若 $n_1, n_2, \dots, n_k$ 两两互素，则同余方程组

$$x \equiv a_i \pmod{n_i}, \quad i = 1, \dots, k$$

在模 $N = \prod n_i$ 下有唯一解。

### 素数

- **算术基本定理**：每个大于 1 的正整数可唯一分解为素数之积。
- **素数无穷**：欧几里得证明。
- **素数定理**：$\pi(n) \sim n / \ln n$。

## 关联概念

- [[algebraic-structures]] — $\mathbb{Z}/n\mathbb{Z}$ 在模运算下构成环；$n$ 为素数时为域。
