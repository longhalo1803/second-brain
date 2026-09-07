---
title: "What is the recurrence equation for the Knapsack with repetition and what is the u..."
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
  - "What is the recurrence equation for the Knapsack with repetition and what is the u..."
---

# 🎴 What is the recurrence equation for the Knapsack with repetition and what is the u...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What is the recurrence equation for the Knapsack with repetition and what is the underlying principle? #card

?

```text
K(w) = _{i \,:\, w_i ≤ w} { v_i + K([.5pt]{w - w_i}_{{remaining
capacity}}) }
```

If we knew for certain that item $i$ belongs to the optimal solution for capacity $w$, by optimal substructure the maximum value would be given by **the value of the item itself (**$v_i$**) added to the optimal value achievable from the remaining space**: $K(w - w_i)$.

Since we do not know in advance which item is optimal, we examine all possible feasible candidates ($i$ such that $w_i \le w$) and select the one that **maximizes** the sum of its own value and the remaining optimum.

📌 Note:
The formula allows _repetition_ because in the remaining subproblem $K(w - w_i)$ all items (including $i$) are available again for selection.
