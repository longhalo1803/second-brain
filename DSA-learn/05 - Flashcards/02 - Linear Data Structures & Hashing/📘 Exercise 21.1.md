---
title: "📘 Exercise 21.1"
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
  - "📘 Exercise 21.1"
---

# 🎴 📘 Exercise 21.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: 📘 Exercise 21.1

**Input:** An array $A$ of $n \ge 2$ integers (not necessarily positive).
**Output:** The maximum product obtainable by multiplying two distinct elements of $A$.

Provide pseudocode of an algorithm with $O(n)$ computational complexity, strictly faster than $O(n^2)$. #card
?
**Reasoning:**
The maximum product of two numbers can come from either the two largest positive numbers or the two smallest (most negative) numbers. Finding the two largest and two smallest elements takes a single linear scan.

**Pseudocode:**

```text
Algorithm MaxPairProduct(A, n):
    max_1 ≤ftarrow -∈fty, \; max_2 ≤ftarrow -∈fty
    min_1 ≤ftarrow +∈fty, \; min_2 ≤ftarrow +∈fty
    for i ≤ftarrow 0 to n - 1 do
        if A[i] > max_1 then
            max_2 ≤ftarrow max_1; \; max_1 ≤ftarrow A[i]
        else if A[i] > max_2 then
            max_2 ≤ftarrow A[i]
        if A[i] < min_1 then
            min_2 ≤ftarrow min_1; \; min_1 ≤ftarrow A[i]
        else if A[i] < min_2 then
            min_2 ≤ftarrow A[i]
    return (max_1 max_2, \; min_1 min_2)
```

**Complexity:**
A single pass over the array takes $\Theta(n)$ time and $O(1)$ auxiliary space.
