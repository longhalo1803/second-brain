---
title: "What is the formal formulation of the Knapsack Problem and what are its two main v..."
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
  - "What is the formal formulation of the Knapsack Problem and what are its two main v..."
---

# 🎴 What is the formal formulation of the Knapsack Problem and what are its two main v...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: What is the formal formulation of the Knapsack Problem and what are its two main variants? #card

?
**Problem formulation:**

- **Input:**
- A knapsack with integer capacity $W \ge 0$;
- A set of $n$ items $\{1, 2, \dots, n\}$;
- Weights of the items: $w_1, w_2, \dots, w_n \in \mathbb{N}$;
- Values of the items: $v_1, v_2, \dots, v_n \in \mathbb{N}$.
- **Output:** A selection of items having total weight less than or equal to $W$ that maximizes the total value of the selected items.**Main variants:**

- **Without repetition (0-1 Knapsack):** each item can be selected at most _once_;
- **With repetition (Unbounded Knapsack):** each item can be selected _multiple times_ (an arbitrary number of times).

  📝 Example:

  W = 10

          item
          weight
          value




          1
          6
          30


          2
          3
          14


          3
          4
          16


          4
          2
          9

  Optimal solution

        **With repetition:**

        1 item 1 + 2 item 4

        → weight 10, value 48

-       **Without repetition:**

        1 item 1 + 1 item 3

        → weight 10, value 46
