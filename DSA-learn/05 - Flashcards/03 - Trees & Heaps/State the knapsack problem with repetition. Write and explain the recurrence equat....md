---
title: "State the knapsack problem with repetition. Write and explain the recurrence equat..."
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
  - "State the knapsack problem with repetition. Write and explain the recurrence equat..."
---

# 🎴 State the knapsack problem with repetition. Write and explain the recurrence equat...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: ❓ State the knapsack problem with repetition. Write and explain the recurrence equation used by the dynamic programming algorithm seen previously. #card

?

- **Statement of the Knapsack Problem with Repetition (Unbounded Knapsack):**
  Given a knapsack of maximum integer capacity $C$ and a set of $n$ item types numbered from $1$ to $n$, each characterized by an integer weight $w_i > 0$ and an economic value $v_i > 0$. An arbitrary and unlimited number of copies of each item may be taken. The objective is to maximize the total value carried without exceeding capacity $C$.
- **Dynamic Programming Recurrence Equation:**
  We define subproblem $K(w)$ as the maximum value achievable with a remaining capacity of $w$, where $0 \le w \le C$:

$$

K(w) = \begin{cases}
0 & \text{if } w = 0 \\
\max\_{\substack{1 \le i \le n \\ w_i \le w}} \{ K(w - w_i) + v_i \} & \text{if there exists } i \text{ with } w_i \le w \\
0 & \text{otherwise (no item fits)}
\end{cases}

$$

- **Explanation of the Equation:**
  For a generic capacity $w$, consider which item to insert _last_:
- Test all candidate items $i$ whose weight does not exceed current capacity ($w_i \le w$).
- If we decide to insert item $i$, we collect its immediate value $v_i$ and are left with a knapsack of reduced capacity $w - w_i$.
- Since copies are unlimited, item $i$ may be chosen again in the remaining subproblem $K(w - w_i)$.
- The optimal value is achieved by picking the item $i$ that maximizes the sum $K(w - w_i) + v_i$.
- The algorithm computes values from $w = 1$ to $C$ with time cost $\mathcal{O}(n \cdot C)$ and space $\mathcal{O}(C)$.
