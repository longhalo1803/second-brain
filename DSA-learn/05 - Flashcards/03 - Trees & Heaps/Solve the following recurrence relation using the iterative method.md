---
title: "Solve the following recurrence relation using the iterative method"
tags:
  - dsa
  - flashcards
  - clrs
  - trees-heaps
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "Solve the following recurrence relation using the iterative method"
---

# 🎴 Solve the following recurrence relation using the iterative method

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📝 Solve the following recurrence relation using the **iterative method**:

$$
T(n) = \begin{cases} 0 & \text{if } n = 0 \\ T(n-1) + d & \text{if } n > 0 \end{cases}
$$ #card
?
We proceed by successive iterations:


$$

\begin{aligned} T(n) &= T(n-1) + d \\ &= [T(n-2) + d] + d = T(n-2) + 2d \\ &= [T(n-3) + d] + 2d = T(n-3) + 3d \\ &= \dots \\ &= T(n-i) + i \cdot d \end{aligned}

$$

The base case is reached when $n-i = 0 \implies i = n$.
Substituting $i = n$ into the expression we get:


$$

T(n) = T(0) + n \cdot d = 0 + nd = nd

$$

Thus, the computational cost is $T(n) \in \Theta(n)$.
$$
