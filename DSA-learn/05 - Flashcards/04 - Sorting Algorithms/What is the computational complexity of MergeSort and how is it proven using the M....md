---
title: "What is the computational complexity of MergeSort and how is it proven using the M..."
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
  - "What is the computational complexity of MergeSort and how is it proven using the M..."
---

# 🎴 What is the computational complexity of MergeSort and how is it proven using the M...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What is the computational complexity of MergeSort and how is it proven using the Master Theorem? #card

?
**Recurrence equation of MergeSort:**
Let $T(n)$ be the running time on an array of size $n$:

$$
T(n) = \begin{cases} 0 & \text{if } n = 1 \\ 2 \cdot T(n/2) + O(n) & \text{if } n > 1 \end{cases}
$$

where:

- $2 \cdot T(n/2)$ represents the cost of the two recursive calls on half of the array;
- $O(n)$ is the cost of the `Merge` procedure (which performs $O(n)$ comparisons and moves to merge the two halves).
  **Resolution using the Master Theorem:**
  The equation is in the standard form $T(n) = a T(n/b) + f(n)$, where:
- $a = 2$ (number of recursive subproblems)
- $b = 2$ (division factor of the input size)
- $f(n) = O(n) = \Theta(n^d)$ with $d = 1$Let us compute $\log_b a$:

$$
\log_b a = \log_2 2 = 1
$$

Since $\log_b a = 1 = d$, we fall into **Case 2 of the Master Theorem**:

$$
T(n) \in \Theta(n^d \log n) = \Theta(n \log n) \implies \boxed{O(n \log n)}
$$

📌 **Optimality:**
MergeSort guarantees a complexity of **$O(n \log n)$ in the worst, average, and best cases**.
No comparison-based sorting algorithm can have a better asymptotic complexity in the worst case.
