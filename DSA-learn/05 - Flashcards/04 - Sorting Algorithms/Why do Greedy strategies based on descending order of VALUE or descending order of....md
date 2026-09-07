---
title: "Why do Greedy strategies based on descending order of VALUE or descending order of..."
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
  - "Why do Greedy strategies based on descending order of VALUE or descending order of..."
---

# 🎴 Why do Greedy strategies based on descending order of VALUE or descending order of...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: Why do Greedy strategies based on **descending order of VALUE** or **descending order of WEIGHT** fail for the Knapsack Problem? #card

?
Both greedy strategies do not guarantee an optimal solution because making a locally advantageous choice (the most valuable or heaviest item) can take up space and prevent globally better combinations.

📝 **Counterexample:**
Let the knapsack capacity be $W$. Consider 3 items:
• Item 1: weight $= W$, value $= 30$
• Item 2: weight $= W/2$, value $= 20$
• Item 3: weight $= W/2$, value $= 15$

**Greedy Outcome:**
Whether sorting by _descending value_ or by _descending weight_, the first item chosen is Item 1 (weight $W$, value 30). The knapsack is filled and the algorithm terminates.
Value obtained: **30**.

**Optimal Solution:**
• **With repetition:** 2 times Item 2 $\rightarrow$ weight $W$, value $20 + 20 =$ **40**.
• **Without repetition:** Item 2 + Item 3 $\rightarrow$ weight $W$, value $20 + 15 =$ **35**.

In both cases, the greedy approach fails.

    📝 Example 1:

    W




          item
          weight
          value




          1
          W
          30


          2
          W/2
          20


          3
          W/2
          15





    Greedy solution


      1 item 1

      → weight W, value 30




    Optimal solution



        **With repetition:**

        2 item 2

        → weight W, value 40

-
**Without repetition:**

        1 item 2 + 1 item 3

        → weight W, value 35
