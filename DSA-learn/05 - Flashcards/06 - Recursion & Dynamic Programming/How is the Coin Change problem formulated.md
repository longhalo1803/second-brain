---
title: "How is the Coin Change problem formulated"
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
  - "How is the Coin Change problem formulated"
---

# 🎴 How is the Coin Change problem formulated

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: How is the Coin Change problem formulated?

Try solving it with the _greedy_ approach. Does it always work? Show a successful example and a counterexample. #card
?

- **INPUT:** A set of available coin denominations (e.g., $50, 10, 5, 1$ cents) and an integer value of _change_ $R$.
- **OUTPUT:** A selection of coins (possibly with repetition) that sum up exactly to $R$ and that are as few as possible.
- **Feasible solution:** Any selection of coins whose sum equals $R$.
- **Solution cost:** Total number of coins present in the selection.
- **Objective function:** **Minimum**.
- **Optimal solution:** Feasible selection with the absolute minimum number of coins.
  **The greedy approach does NOT always work for any set of coin denominations!**

Greedy strategy: choose at each step the coin of maximum possible value that is $\le$ to the remaining change.

📝 **Case 1 - With denominations **$\{50, 10, 5, 1\}$** and change **$72$**:**

- Greedy choice: $50 + 10 + 10 + 1 + 1 = 72$
- Result: **5 coins**. In this case, the Greedy algorithm works and returns the optimum! ✅

⚠️ **Case 2 (counterexample) - With denominations **$\{11, 5, 1\}$** and change **$15$**:**
**GREEDY Approach:**

1. Takes the 11 coin (change left: 4)
2. Takes four 1 coins
   Result: $11 + 1 + 1 + 1 + 1 = 15$
   Cost: **5 coins** ❌**OPTIMAL Solution:**
3. Takes three 5 coins
   Result: $5 + 5 + 5 = 15$
   Cost: **3 coins** ✅
   The correctness of a greedy algorithm therefore strongly depends on the mathematical properties of the specific instance/structure of the problem.
