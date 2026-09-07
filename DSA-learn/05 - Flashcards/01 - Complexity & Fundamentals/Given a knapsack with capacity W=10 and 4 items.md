---
title: "Given a knapsack with capacity W=10 and 4 items"
tags:
  - dsa
  - flashcards
  - clrs
  - complexity
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "Given a knapsack with capacity W=10 and 4 items"
---

# 🎴 Given a knapsack with capacity W=10 and 4 items

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: 📝 Given a knapsack with capacity $W=10$ and 4 items

$(w_1=6, v_1=30)$,
$(w_2=3, v_2=14)$,
$(w_3=4, v_3=16)$,
$(w_4=2, v_4=9)$,
what is the optimal value and which items make up the solution?

      i \ w
      0
      1
      2
      3
      4
      5
      6
      7
      8
      9
      10


      0
      0
      0
      0
      0
      0
      0
      0
      0
      0
      0
      0


      1 (6, 30)
      0






















      2 (3, 14)
      0






















      3 (4, 16)
      0






















      4 (2, 9)
      0


















      **?** #card

?
Computed subproblem matrix $K(i, w)$:

      i \ w
      0
      1
      2
      3
      4
      5
      6
      7
      8
      9
      10


      0
      0
      0
      0
      0
      0
      0
      0
      0
      0
      0
      0


      1 (6, 30)
      0
      0
      0
      0
      0
      0
      30
      30
      30
      30
      30


      2 (3, 14)
      0
      0
      0
      14
      14
      14
      30
      30
      30
      44
      44


      3 (4, 16)
      0
      0
      0
      14
      16
      16
      30
      30
      30
      44
      46


      4 (2, 9)
      0
      0
      9
      14
      16
      23
      30
      30
      39
      44
      **46**

```text
K(i,w) = {cases} K(i-1, w) se w_i > w
{cases} K(i-1, w)
v_i + K(i-1, w - w_i) {cases} {cases}
```

**Maximum achievable value:** $K(4, 10) = 46$

**Reconstruction of chosen items (_backtracking_):**

- $K(4, 10) = K(3, 10) = 46 \implies$ **Item 4 NO**.
- $K(3, 10) = 46 \ne K(2, 10) = 44 \implies$ **Item 3 YES**. Remaining capacity: $10 - 4 = \textcolor{red}{6}$.
- $K(2, \textcolor{red}{6}) = K(1, 6) = 30 \implies$ **Item 2 NO**.
- $K(1, 6) = 30 \ne K(0, 6) = 0 \implies$ **Item 1 YES**.

📝 Example: the selected items are **Item 1** and **Item 3** (total weight $6+4=10$, total value $30+16=46$).
