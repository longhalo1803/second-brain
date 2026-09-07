---
title: "Why do Greedy strategies based on ascending order of WEIGHT or descending order of..."
tags:
  - dsa
  - flashcards
  - clrs
  - dynamic-programming
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "Why do Greedy strategies based on ascending order of WEIGHT or descending order of..."
---

# 🎴 Why do Greedy strategies based on ascending order of WEIGHT or descending order of...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: Why do Greedy strategies based on **ascending order of WEIGHT** or **descending order of VALUE DENSITY (value per unit of weight: $v_i/w_i$)** fail for the Knapsack Problem? #card

?
These greedy strategies also fail to guarantee the global optimum:

**1. Ascending order of weight:**
Let the knapsack capacity be $W$. Items:
• Item 1 ($w=W, v=30$),
• Item 2 ($w=3W/4, v=20$),
• Item 3 ($w=W/2, v=15$).

- _Greedy:_ chooses Item 3 (smallest weight $W/2$, value 15). Remaining capacity is $W/2$, in which no other item can fit. Value obtained: **15**.
- _Optimal:_ Item 1 (weight $W$, value **30**).

  📝 Example 2:

  W

          item
          weight
          value




          1
          W
          30


          2
          3W/4
          20


          3
          W/2
          15

  Greedy solution

      1 item 3

      → weight W/2, value 15

  Optimal solution

        **With repetition:**

        1 item 1

        → weight W, value 30

-       **Without repetition:**

        1 item 1

        → weight W, value 30

** 2. Descending order of density ($v_i/w_i$):**
Let the capacity be $W = 10$. Items:
• Item 1: weight $= 10$, value $= 30$ $\rightarrow v_1/w_1 = 3$
• Item 2: weight $= 6$, value $= 28$ $\rightarrow v_2/w_2 \approx 4.66$

- _Greedy:_ chooses the item with maximum density ($v_i/w_i$), i.e. Item 2 (weight 6, value 28). Remaining capacity is $10 - 6 = 4$, insufficient to insert any other item. Value obtained: **28**.
- _Optimal:_ Item 1 (weight 10, value **30**).

  📝 Example 3:

  W = 10

          item
          weight
          value
          v/w




          1
          10
          30
          30/10 = 3


          2
          6
          28
          28/6 = 4.66

  Greedy solution

      1 item 2

      → weight 6, value 28

  Optimal solution

        **With repetition:**

        1 item 1

        → weight 10, value 30

-       **Without repetition:**

        1 item 1

        → weight 10, value 30
