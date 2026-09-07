---
title: "Exercise 11"
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
  - "Exercise 11"
---

# 🎴 Exercise 11

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📝 Exercise 11

Write an efficient procedure that, given as input a sequence of $n$ integers between 0 and $m$ with $m \in O(n)$ in an array $L$ and an integer $k$, prints only the values in $L$ that appear exactly $k$ times. Analyze the computational complexity of the proposed solution.

_Hint:_ use a process similar to that of `CountingSort` (non-stable version). #card
?
**Pseudocode of the procedure:**

```text
Print(L, n, m, k)
    C[0..m] new array
    for i := 0 to m do
        C[i] := 0
    for j := 0 to n - 1 do
        C[L[j]] := C[L[j]] + 1
    for i := 0 to m do
        if C[i] = k then
            print i
```

**Computational cost: **is given by the sum of the costs of the three `for` loops:

- The first loop costs $O(m)$;
- The second loop costs $O(n)$;
- The third loop costs again $O(m)$.In total, the cost is $O(m + n)$. Since by assumption $m \in O(n)$, the overall cost of the algorithm is **$O(n)$**.
