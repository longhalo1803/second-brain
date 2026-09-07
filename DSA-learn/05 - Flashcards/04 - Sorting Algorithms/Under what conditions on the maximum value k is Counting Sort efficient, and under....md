---
title: "Under what conditions on the maximum value k is Counting Sort efficient, and under..."
tags:
  - dsa
  - flashcards
  - clrs
  - sorting
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "Under what conditions on the maximum value k is Counting Sort efficient, and under..."
---

# 🎴 Under what conditions on the maximum value k is Counting Sort efficient, and under...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: Under what conditions on the maximum value $k$ is Counting Sort efficient, and under what conditions does it become inefficient? #card

?
**Favorable case:**

- If $k \in O(n) \implies T(n) \in O(n)$ (**linear** time).
- If $k \in O(n \log n) \implies T(n) \in O(n \log n)$.
- It is ideally used when $k \in O(n)$, and especially if $k \in \Theta(1)$ or $k \le n$.
  ⚠️ **Unfavorable case:**
- If $k \in \Omega(n^t)$ with $t > 1 \implies T(n) \in \Omega(n^t)$ and Space $\Theta(n^t)$ (e.g. polynomial/quadratic if values are very large).
- If $k \in \Omega(2^n) \implies T(n) \in \Omega(2^n)$ and Space $\Theta(2^n)$ (exponential).
  📌 Note:
  Counting Sort is convenient only if the range of values $k$ is comparable to the size $n$ of the input.
