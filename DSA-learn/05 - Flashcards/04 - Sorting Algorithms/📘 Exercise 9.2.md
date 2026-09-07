---
title: "📘 Exercise 9.2"
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
  - "📘 Exercise 9.2"
---

# 🎴 📘 Exercise 9.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📘 Exercise 9.2

Design a recursive Divide and Conquer algorithm that finds the second largest element of an unsorted array $A$ of natural numbers without modifying $A$ or copying it into another array.

Describe the base and recursive cases, provide the pseudocode, write the recurrence relation for the worst-case runtime, and solve it. #card
?
**Reasoning:**
A Divide and Conquer approach can split the array in half and recursively return both the largest and the second largest elements of each half. Combining the results requires only a few constant-time comparisons.

**Base Case and Recursive Case:**

- _Base Cases:_ Range of size 2: return $(\max, \min)$. Range of size 1: return $(A[low], -\infty)$.
- _Recursive Case:_ Split at $mid = \lfloor (low + high)/2 \rfloor$. Recursively solve left half $(M_1, S_1)$ and right half $(M_2, S_2)$. The overall maximum is $M = \max(M_1, M_2)$. The overall second maximum is $\max(\min(M_1, M_2), S_1, S_2)$.
  **Pseudocode:**

```text
Function FindTopTwo(A, low, high):
    if low = high then return (A[low], -∈fty)
    if low + 1 = high then
        if A[low] ≥ A[high] then return (A[low], A[high])
        else return (A[high], A[low])
    mid ≤ftarrow floor( (low + high) / 2 )
    (M_1, S_1) ≤ftarrow FindTopTwo(A, low, mid)
    (M_2, S_2) ≤ftarrow FindTopTwo(A, mid + 1, high)
    if M_1 > M_2 then
        return (M_1, (M_2, S_1))
    else
        return (M_2, (M_1, S_2))

Algorithm SecondLargest(A, n):
    (M, S) ≤ftarrow FindTopTwo(A, 0, n - 1)
    return S
```

**Recurrence and Complexity:**

```text
T(n) = 2T(n/2) + O(1), T(2) = O(1)
```

By the Master Theorem ($a = 2, b = 2, f(n) = O(1)$), $n^{\log_2 2} = n^1$. Thus, $T(n) = \Theta(n)$.
