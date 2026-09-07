---
title: "📘 Exercise 24.1"
tags:
  - dsa
  - flashcards
  - clrs
  - data-structures
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "📘 Exercise 24.1"
---

# 🎴 📘 Exercise 24.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: 📘 Exercise 24.1

**Input:** An array $A$ of $n$ distinct integers formed by a circular shift of $k$ positions to the right of an increasing sequence ($k \in [0, n - 1]$).
**Output:** The minimum value in $A$.

- Show examples with $n \ge 10$ for $k = 0$ and $k = \lceil n/3 \rceil$.
- Describe a sublinear algorithm in words and provide pseudocode.
- Does the algorithm work if values in $A$ are not distinct? Argue your answer. #card
  ?
  **Reasoning:**
  If $A[mid] > A[high]$, the minimum must be strictly in the right half $[mid + 1, high]$. If $A[mid] A[high] then
  low ≤ftarrow mid + 1
  else
  high ≤ftarrow mid
  return A[low]

```

 Complexity is $O(\log n)$ time and $O(1)$ space.

**3. Non-distinct Elements:**
No, it does not guarantee $O(\log n)$ time if duplicates are allowed. When $A[low] = A[mid] = A[high]$ (e.g. $[2, 2, 2, 0, 2]$), one cannot determine which half contains the minimum without linearly scanning, degrading the worst-case runtime to $\Theta(n)$.
```
