---
title: "Explain what principles the ”Divide and Conquer” technique is based on in general,..."
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
  - "Explain what principles the ”Divide and Conquer” technique is based on in general,..."
---

# 🎴 Explain what principles the ”Divide and Conquer” technique is based on in general,...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: ❓ Explain what principles the ”Divide and Conquer” technique is based on in general, and show how it applies, in particular, to the sorting problem in the MergeSort algorithm. Why is the ”Divide and Conquer” technique well-suited to using the Master Theorem for computing computational costs? #card

?

- **Principles of the "Divide and Conquer" Paradigm:**
  The paradigm breaks down the solution of a complex problem into three logical phases:
- **Divide:** Split the original problem into a number $a \ge 1$ of independent subproblems, which are smaller instances of the same problem (typically a fraction $1/b$ of the original size).
- **Conquer:** Solve the subproblems recursively. If a subproblem's size is small enough (base case), solve it directly without further recursion.
- **Combine:** Combine the solutions of individual subproblems into the solution for the original instance.
- **Application to the MergeSort Algorithm:**
  MergeSort sorts an array $A[p \dots r]$ by strictly applying the three phases:
- **Divide:** Compute the midpoint $q = \lfloor (p+r)/2 \rfloor$ and split the array into two contiguous halves: $A[p \dots q]$ and $A[q+1 \dots r]$. This step takes constant time $\mathcal{O}(1)$.
- **Conquer:** Recursively call MergeSort on the two halves, each of size approximately $n/2$. The base case is reached when sequence length is $\le 1$, which is trivially sorted.
- **Combine:** Merge the two sorted halves into a single globally sorted sequence by invoking the `Merge` procedure. `Merge` traverses both subarrays linearly, comparing their leading elements and placing the smaller one into an auxiliary array, at strictly linear time cost $\Theta(n)$.
- **Why it is well-suited to the Master Theorem:**
  Divide and Conquer algorithms partition an input of size $n$ into $a$ subproblems of size $n/b$, spending $f(n)$ time on the divide and combine steps. The total running time is naturally expressed as a recurrence relation in canonical form:

$$

T(n) = a \, T(n/b) + f(n)

$$

The **Master Theorem** is an analytical tool designed specifically to solve this family of recurrences directly. It compares the cost of work done at the leaves of the recursion tree, expressed by function $n^{\log_b a}$, against the cost of dividing and combining at internal levels, $f(n)$:

- If work at the leaves dominates, the solution is $T(n) = \Theta(n^{\log_b a})$.
- If the work cost is balanced at each level of recursion, the solution is $T(n) = \Theta(n^{\log_b a} \log n)$ (as in MergeSort, where $a=2, b=2, f(n)=\Theta(n) \implies n^{\log_2 2} = n^1$, leading to $\Theta(n \log n)$).
- If the root combination function $f(n)$ dominates, the solution is $T(n) = \Theta(f(n))$.
