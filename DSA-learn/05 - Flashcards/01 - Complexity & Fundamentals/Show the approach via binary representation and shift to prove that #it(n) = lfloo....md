---
title: "Show the approach via binary representation and shift to prove that #it(n) = lfloo..."
tags:
  - dsa
  - flashcards
  - clrs
  - complexity
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "Show the approach via binary representation and shift to prove that #it(n) = lfloo..."
---

# 🎴 Show the approach via binary representation and shift to prove that #it(n) = lfloo...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: Show the approach via **binary representation and shift** to prove that $\#it(n) = \lfloor\log_2 n\rfloor + 1$ (alternative to induction). #card

?
Let $k$ be such that:

$$
2^k \le n < 2^{k+1} \implies k = \lfloor\log_2 n\rfloor
$$

This implies that the number $n$ can be represented in binary using exactly $k + 1$ bits.

At each iteration, the remaining portion has at most $\lfloor n / 2^i \rfloor$ elements. This operation mathematically corresponds to performing a **right shift** by $i$ positions on the binary representation of $n$.

To reduce the number of binary digits to zero (i.e., to exhaust the elements and reach an empty portion), exactly:

$$
k + 1 = \lfloor\log_2 n\rfloor + 1 \text{ shifts (iterations)}
$$

are required.
