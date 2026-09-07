---
title: "What is the computational complexity of the algorithm for Knapsack with repetition..."
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
  - "What is the computational complexity of the algorithm for Knapsack with repetition..."
---

# 🎴 What is the computational complexity of the algorithm for Knapsack with repetition...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: What is the computational complexity of the algorithm for Knapsack with repetition and why is it called _pseudo-polynomial_? #card

?

```text
Knapsack_With_Repetition(W, n, w, v)
    min := _{i ∈ [1..n]} { w_i }
    for w := 0 to min - 1 do
        K[w] := 0
    for w := min to W do
        K[w] := _{i : w_i ≤ w} { v_i + K[w - w_i] } // {#D9534F}{≤ftarrow O(n)}
    return K[W]
```

**Time and space complexity:**

- **Time:** $O(W \cdot n)$.
  The outer loop executes $W$ times; at each iteration, finding the maximum examines at most $n$ items, performing $O(n)$ elementary operations.
- **Space:** $O(W)$ to store the one-dimensional array of subproblems $K[0..W]$.**Why is it pseudo-polynomial?**
  An algorithm is called _pseudo-polynomial_ when its time complexity is polynomial with respect to the **numerical value** of an input datum (in this case $W$), but exponential with respect to the **length of its representation** in bits.

Indeed, the integer $W$ is represented using $b = \lceil \log_2(W + 1) \rceil$ bits.
Expressing the cost as a function of the input size $b$ yields a time complexity of $O(n \cdot 2^b)$, which is formally **exponential**.
