---
title: "Exercise 8"
tags:
  - dsa
  - flashcards
  - clrs
  - dynamic-programming
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "Exercise 8"
---

# 🎴 Exercise 8

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: 📝 **Exercise 8***

Given an $n\times n$ matrix of integers, for $n$ a power of 2, write a function that determines the minimum element in $M$ using the **divide-and-conquer** technique.

💡 **Hint**Divide the matrix into four submatrices of size $n/2\times n/2$. Pay attention to the indices!
It is necessary to define a way to indicate the matrix being considered. Example: pair of indices $(i, j)$ for the top-left corner of the matrix, plus a value $m$ indicating the size. The top-right corner will be at $(i, i+m-1)$; or a triple $(i, j, k)$ where $(i,j)$ indicates top-left and $k$ the column index of the top-right corner, with size $m=k-i+1$. #card
?
The algorithm divides the current matrix $m \times m$ into 4 submatrices of size $\frac{m}{2} \times \frac{m}{2}$, recursively computes the minimum of each, and returns the global minimum among the four values.

We represent the submatrix using the coordinates of the top-left corner $(r, c)$ and the current size $m$.

```text
DivideAndConquerMatrixMin(M, r, c, m)
    // Base Case: 1x1 submatrix
    if m = 1 then return M[r][c]
    // Divide and Conquer
    new_m := m / 2
    min1 := DivideAndConquerMatrixMin(M, r, c, new_m) // Top-Left
    min2 := DivideAndConquerMatrixMin(M, r, c + new_m, new_m) // Top-Right
    min3 := DivideAndConquerMatrixMin(M, r + new_m, c, new_m) // Bottom-Left
    min4 := DivideAndConquerMatrixMin(M, r + new_m, c + new_m, new_m) // Bottom-Right
    return min(min1, min(min2, min(min3, min4)))
```

Main call for an $n \times n$ matrix: $\textsf{DivideAndConquerMatrixMin(M, 0, 0, n)}$.

**Cost analysis (Recurrence Relation):**
The associated recurrence relation is:

$$

T(m) = 4T(m/2) + \Theta(1)

$$

Applying the Master Theorem with $a=4, b=2, d=0$, we compare $\log_b a = \log_2 4 = 2$ with $d=0$.
Since $\log_2 4 > 0$, we fall into the first case of the Master Theorem, obtaining a computational cost equal to:

$$

T(m) \in \Theta(m^{\log_2 4}) = \Theta(m^2)

$$

For the initial matrix of size $n$, the total cost is $\Theta(n^2)$, which is optimal since it visits each cell of the matrix exactly once.
