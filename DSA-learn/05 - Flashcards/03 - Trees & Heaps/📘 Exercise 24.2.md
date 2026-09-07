---
title: "📘 Exercise 24.2"
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
  - "📘 Exercise 24.2"
---

# 🎴 📘 Exercise 24.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 24.2

**Input:** A square matrix $M$ of size $n \times n$ where $n = 2^k$ ($k \ge 0$) and $M[i, j] \in \{0, 1\}$.
**Output:** The total number of 1s in $M$.

- Describe a Divide and Conquer algorithm and provide pseudocode.
- Analyze its computational complexity.
- Explain how to modify it for rectangular matrices $n \times m$. #card
  ?
  **Reasoning:**
  Divide the matrix into 4 equal sub-matrices of size $n/2 \times n/2$, recursively count 1s in each, and sum the four results.

**Pseudocode:**

```text
Function CountOnes(M, r_1, c_1, size):
    if size = 1 then return M[r_1][c_1]
    half ≤ftarrow size / 2
    c_1 ≤ftarrow CountOnes(M, r_1, c_1, half)
    c_2 ≤ftarrow CountOnes(M, r_1, c_1 + half, half)
    c_3 ≤ftarrow CountOnes(M, r_1 + half, c_1, half)
    c_4 ≤ftarrow CountOnes(M, r_1 + half, c_1 + half, half)
    return c_1 + c_2 + c_3 + c_4
```

**Complexity:**
Recurrence: $T(n) = 4T(n/2) + O(1)$. By Master Theorem, $n^{\log_2 4} = n^2$. Total time: $\Theta(n^2)$, which is linear in the number of entries.

**Rectangular Extension:**
For $n \times m$, if $n > 1$ and $n \ge m$, split horizontally into two matrices of size $\lfloor n/2 \rfloor \times m$ and $\lceil n/2 \rceil \times m$. If $m > 1$ and $m > n$, split vertically into two matrices of size $n \times \lfloor m/2 \rfloor$ and $n \times \lceil m/2 \rceil$. Base case: $1 \times 1$ returns $M[r][c]$.
