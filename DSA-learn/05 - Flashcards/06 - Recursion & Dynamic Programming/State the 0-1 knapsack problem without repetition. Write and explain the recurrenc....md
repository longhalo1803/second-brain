---
title: "State the 0-1 knapsack problem without repetition. Write and explain the recurrenc..."
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
  - "State the 0-1 knapsack problem without repetition. Write and explain the recurrenc..."
---

# 🎴 State the 0-1 knapsack problem without repetition. Write and explain the recurrenc...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: ❓ State the 0-1 knapsack problem without repetition. Write and explain the recurrence equation used by the dynamic programming algorithm seen previously. #card

?

- **Statement of the Knapsack Problem without Repetition (0/1 Knapsack):**
  Given a knapsack with integer capacity $C$ and $n$ distinct items, each with integer weight $w_i > 0$ and value $v_i > 0$. Each item may be placed in the knapsack **at most once** (binary choice: taken or not taken). The objective is to maximize the total value of selected items without total weight exceeding $C$.
- **Dynamic Programming Recurrence Equation:**
  We define subproblem $K(i, w)$ as the maximum value achievable choosing from a subset of the first $i$ items (with $0 \le i \le n$) for a knapsack of capacity $w$ (with $0 \le w \le C$):

$$

K(i, w) = \begin{cases}
0 & \text{if } i = 0 \text{ or } w = 0 \\
K(i-1, w) & \text{if } w_i > w \\
\max \big( K(i-1, w), \; K(i-1, w - w_i) + v_i \big) & \text{if } w_i \le w
\end{cases}

$$

- **Explanation of the Equation:**
  To determine the optimal solution considering the first $i$ items and capacity $w$, there are only two alternatives regarding the $i$-th item:
- **Do not include item $i$:** The maximum value will be that obtained using only the first $i-1$ items with the same capacity $w$, namely $K(i-1, w)$. This choice is mandatory if $w_i > w$.
- **Include item $i$ (if $w_i \le w$):** Gain value $v_i$ and remaining capacity decreases to $w - w_i$. The remaining space must be filled optimally by choosing from the first **$i-1$** remaining items (guaranteeing that item $i$ is not reused), yielding $K(i-1, w - w_i) + v_i$.
- The algorithm takes the maximum of the two choices, filling an $n \times C$ matrix in $\mathcal{O}(n \cdot C)$ time and space (pseudo-polynomial).
