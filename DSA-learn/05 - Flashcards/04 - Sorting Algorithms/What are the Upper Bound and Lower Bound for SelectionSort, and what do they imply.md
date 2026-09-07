---
title: "What are the Upper Bound and Lower Bound for SelectionSort, and what do they imply"
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
  - "What are the Upper Bound and Lower Bound for SelectionSort, and what do they imply"
---

# 🎴 What are the Upper Bound and Lower Bound for SelectionSort, and what do they imply

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What are the Upper Bound and Lower Bound for SelectionSort, and what do they imply? #card

?
**Upper bound:**
Since each call requires a number of operations upper-bounded by $c_1 \cdot n$:

$$
T(n) \le \begin{cases} 0 & \text{if } n=1 \\ T(n-1) + c_1 \cdot n & \text{otherwise} \end{cases} \implies T(n) \le c_1 \sum_{i=0}^{n} i = c_1 \frac{n(n+1)}{2} \in O(n^2)
$$

**Lower bound:**
Since finding the minimum requires at least $c_2 \cdot n$ operations at each step:

$$
T(n) \ge \begin{cases} 0 & \text{if } n=1 \\ T(n-1) + c_2 \cdot n & \text{otherwise} \end{cases} \implies T(n) \in \Omega(n^2)
$$

**Implication:**

```text
T(n) ∈ O(n^2) and T(n) ∈ (n^2) T(n) ∈ (n^2)
```

⚠️ Warning:
The number of comparisons in SelectionSort is always $\frac{n(n-1)}{2}$, regardless of whether the input array is already sorted, partially sorted, or reversed.
