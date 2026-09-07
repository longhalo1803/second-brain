---
title: "What is the computational complexity of the Dynamic Programming algorithm for the..."
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
  - "What is the computational complexity of the Dynamic Programming algorithm for the..."
---

# 🎴 What is the computational complexity of the Dynamic Programming algorithm for the...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: What is the computational complexity of the Dynamic Programming algorithm for the 0-1 knapsack problem, and why is it defined as "pseudo-polynomial"? #card

?
**Time and Space Complexity:**

- **Time:** $\mathcal{O}(n \cdot W)$ → two nested loops that fill a matrix of size $(n+1) \times (W+1)$.
- **Space:** $\mathcal{O}(n \cdot W)$ → memory required to store the table of subproblems.
  **Why is it Pseudo-Polynomial?**
  The algorithm is **pseudo-polynomial** because its complexity depends on the _numerical value_ of the input parameter $W$, and not on the number of bits used to represent it.
  If the capacity $W$ is encoded in binary using $B = \lceil \log_2 W \rceil$ bits, the complexity grows exponentially with respect to the input size in bits: $\mathcal{O}(n \cdot 2^B)$.
