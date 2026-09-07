---
title: "What is the complexity of InsertionSort in the best case and why is it an adaptive..."
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
  - "What is the complexity of InsertionSort in the best case and why is it an adaptive..."
---

# 🎴 What is the complexity of InsertionSort in the best case and why is it an adaptive...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What is the complexity of InsertionSort in the best case and why is it an "adaptive" algorithm? #card

?
**Best case**: occurs when the input sequence is **already sorted in non-decreasing order**.

**Why?**
At each iteration of the outer loop $j$ (from 1 to $n-1$), the condition of the `while` loop ($A[i] > \textsf{tmp}$, with $i = j-1$) is immediately **false** on the first comparison ($A[j-1] \le A[j]$).

Therefore, the `while` loop is executed exactly **1 single time** for each value of $j$.

**Computational cost in the best case:**

$$
T(n) = \sum_{j=1}^{n-1} 1 = n - 1 \implies T(n) \in \Theta(n)
$$

📌 Note: InsertionSort is an **adaptive** algorithm because it takes advantage of any existing partial or total order in the input data, requiring significantly fewer comparisons than in the worst case (down to linear $\Theta(n)$).
