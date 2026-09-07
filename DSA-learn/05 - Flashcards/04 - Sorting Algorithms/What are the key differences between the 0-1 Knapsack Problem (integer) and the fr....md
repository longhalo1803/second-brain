---
title: "What are the key differences between the 0-1 Knapsack Problem (integer) and the fr..."
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
  - "What are the key differences between the 0-1 Knapsack Problem (integer) and the fr..."
---

# 🎴 What are the key differences between the 0-1 Knapsack Problem (integer) and the fr...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What are the key differences between the 0-1 Knapsack Problem (_integer_) and the _fractional_ Knapsack Problem? #card

?
**1. 0-1 Knapsack (_integer_):**

- **Constraint:** An item must be taken entirely (1) or left behind (0). Fractions are not allowed.
- **Resolution Technique:** Dynamic Programming.
- **Complexity:** $\mathcal{O}(n \cdot W)$ (pseudo-polynomial, NP-hard problem).
  **2. _Fractional_ Knapsack:**

- **Constraint:** It is possible to take an arbitrary fraction of each item.
- **Resolution Technique:** Greedy Algorithm (sorting by value density $v_i / w_i$).
- **Complexity:** $\mathcal{O}(n \log n)$ (polynomial time, bound by the sorting cost).
  📌 Note: the Greedy approach fails on the 0-1 knapsack problem, for which Dynamic Programming is essential.
