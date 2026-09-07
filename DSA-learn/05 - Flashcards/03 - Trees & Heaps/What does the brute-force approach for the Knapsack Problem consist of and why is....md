---
title: "What does the brute-force approach for the Knapsack Problem consist of and why is..."
tags:
  - dsa
  - flashcards
  - clrs
  - trees-heaps
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "What does the brute-force approach for the Knapsack Problem consist of and why is..."
---

# 🎴 What does the brute-force approach for the Knapsack Problem consist of and why is...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What does the brute-force approach for the Knapsack Problem consist of and why is it not viable? #card

?
It consists of generating all possible selections/combinations of items, checking for each whether the total weight satisfies the capacity constraint ($\le W$), computing its total value, and keeping the selection with the maximum value.

The brute-force approach is **computationally intractable**, since the number of possible combinations grows exponentially with the number of items $n$ (or even worse with repetition, where the number of insertable elements is limited only by $W$).

📌 Further details on the exact costs of the brute-force approach:

- **Without repetition (0/1 Knapsack):
  **For each of the $n$ items there are exactly $2$ possible decisions: take it (1) or do not take it (0). The list of items forms a set, and the number of subsets of a set is $2^n$.

- Number of combinations: $2 \times 2 \times \dots \times 2 = 2^n$

- Brute-force complexity: $O(2^n)$

- **With repetition (Unbounded Knapsack):**
  For each item $i$ with weight $w_i$, there are not just $2$ choices, but it can be taken anywhere from $0$ up to $\lfloor W / w_i \rfloor$ times.

-     **Number of combinations:** $\prod_{i=1}^n \left( \left\lfloor \frac{W}{w_i} \right\rfloor + 1 \right)$

-     **Brute-force complexity:** In the worst case (where weights are small compared to $W$), this product is equivalent to an exploration on the order of $O(W^n)$ (or $O(n^{W / w_{\min}})$ if modeled as a decision tree where at each step you choose one of the $n$ items until the knapsack is full).
