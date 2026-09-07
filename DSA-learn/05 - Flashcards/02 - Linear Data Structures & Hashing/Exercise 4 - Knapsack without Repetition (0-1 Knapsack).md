---
title: "Exercise 4 - Knapsack without Repetition (0-1 Knapsack)"
tags:
  - dsa
  - flashcards
  - clrs
  - data-structures
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "Exercise 4 - Knapsack without Repetition (0-1 Knapsack)"
---

# 🎴 Exercise 4 - Knapsack without Repetition (0-1 Knapsack)

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: 📝📍 Exercise 4 - Knapsack without Repetition (0-1 Knapsack)

Given the items and knapsack capacities $W$ described below, determine the maximum value that can be carried by the knapsack assuming each item is unique (0-1 knapsack without repetition).

**(a) $W = 14\text{ kg}$**ItemWeightValue16182320361544295517**(b) $W = 12\text{ kg}$**ItemWeightValue14182623332244185519**(c) $W = 16\text{ kg}$**ItemWeightValue14232529362044165319**(d) $W = 17\text{ kg}$**ItemWeightValue15212323353046165419**(e) $W = 17\text{ kg}$**ItemWeightValue15172423331645165424**(f) $W = 17\text{ kg}$**ItemWeightValue14262623342846285316 #card
?
Formula: $K(i,w) = \begin{cases} ➀\, K(i-1, w) \quad\text{ if } w_i > w \\ ➁\, \max \begin{cases} K(i-1, w) \\ v_i + K(i-1, w - w_i) \end{cases} \end{cases}$

The formula above implies the following mechanism for item $i$:

- **① DOES NOT FIT (**$w_i > w$**) → Copy cell ABOVE**

- Directly copy the value of the cell immediately above: $K(i-1, w)$.

- **Intuition**: item $i$ has a weight greater than the capacity $w$ of the current column. Since it cannot be included, the maximum achievable value remains the one already obtained with the first $i-1$ items.

- **② FITS (**$w_i \le w$**) → MAXIMUM between [ABOVE] and [VALUE + DIAGONALLY BACK]**

- Take the larger value in the cell by comparing the following two:

- **Cell above:** $K(i-1, w)$ (the _do not take_ option).

- **Value $v_i$ + Cell above shifted left by $w_i$ columns:** $v_i + K(i-1, w - w_i)$ (the _take_ option).

- **Intuition**: if one chooses to place item $i$ into the knapsack, its value $v_i$ is gained immediately, but a weight equal to $w_i$ is consumed. To find the maximum value that can be packed into the remaining space, check the row above (previous items) at column $w - w_i$ (remaining capacity in the knapsack).

(Note: Row $i = 0$ (no items available/considered) and column $w = 0$ (knapsack capacity equal to 0), which would be the two base cases of the problem, have been omitted from all tables to reduce visual clutter, starting directly from item $i = 1$ and capacity $w = 1$.)

For **backtracking**, start from the bottom-right corner $K(n, W)$ and trace back up the table by asking at each step: "Was this value copied from the cell above (item $i$ NOT included) or does it come from including item $i$ (INCLUDED, subtract its weight $w_i$ from the current column and move to the row above)?"

      **(a) **$W = 14\text{ kg}$** – Optimal Val.: **$K[5, 14] = 67$** – Selected: $[1,2,4]$**

$$

\small\begin{array}{c|cccccccccccccc}
i \backslash w & 1 & 2 & 3 & 4 & 5 & 6 & 7 & 8 & 9 & 10 & 11 & 12 & 13 & 14 \\
\hline
1 & 0 & 0 & 0 & 0 & 0 & 18 & \color{red}{\boxed{\color{currentColor}{18}}} & 18 & 18 & 18 & 18 & 18 & 18 & 18 \\
2 & 0 & 0 & 20 & 20 & 20 & 20 & 20 & 20 & 38 & \color{red}{\boxed{\color{currentColor}{38}}} & 38 & 38 & 38 & 38 \\
3 & 0 & 0 & 20 & 20 & 20 & 20 & 20 & 20 & 38 & \color{orange}{38} & 38 & 38 & 38 & 38 \\
4 & 0 & 0 & 20 & 29 & 29 & 29 & 49 & 49 & 49 & 49 & 49 & 49 & 67 & \color{red}{\boxed{\color{currentColor}{67}}} \\
5 & 0 & 0 & 20 & 29 & 29 & 29 & 49 & 49 & 49 & 49 & 49 & 66 & 67 & \color{lightgreen}{67} \\
\end{array}

$$

      **(b) $W = 12\text{ kg}$**** – Optimal Val.: **$K[5, 12] = 59$** – Selected:** $[3, 4, 5]$

$$

\small\begin{array}{c|cccccccccccc}
i \backslash w & 1 & 2 & 3 & 4 & 5 & 6 & 7 & 8 & 9 & 10 & 11 & 12 \\
\hline
1 & 0 & 0 & 0 & 18 & 18 & 18 & 18 & 18 & 18 & 18 & 18 & 18 \\
2 & 0 & 0 & 0 & 18 & 18 & 23 & 23 & 23 & 23 & 41 & 41 & 41 \\
3 & 0 & 0 & \color{red}{\boxed{\color{currentColor}{22}}} & 22 & 22 & 23 & 40 & 40 & 45 & 45 & 45 & 45 \\
4 & 0 & 0 & 22 & 22 & 22 & 23 & \color{red}{\boxed{\color{currentColor}{40}}} & 40 & 45 & 45 & 58 & 58 \\
5 & 0 & 0 & 22 & 22 & 22 & 23 & 40 & 41 & 45 & 45 & 58 & \color{red}{\boxed{\color{lightgreen}{59}}} \\
\end{array}

$$

      **(c) $W = 16\text{ kg}$**** – Optimal Val.: **$K[5, 16] = 87$** – Selected:** $[1, 2, 4, 5]$

$$

\small\begin{array}{c|cccccccccccccccc}
i \backslash w & 1 & 2 & 3 & 4 & 5 & 6 & 7 & 8 & 9 & 10 & 11 & 12 & 13 & 14 & 15 & 16 \\
\hline
1 & 0 & 0 & 0 & \color{red}{\boxed{\color{currentColor}{23}}} & 23 & 23 & 23 & 23 & 23 & 23 & 23 & 23 & 23 & 23 & 23 & 23 \\
2 & 0 & 0 & 0 & 23 & 29 & 29 & 29 & 29 & \color{red}{\boxed{\color{currentColor}{52}}} & 52 & 52 & 52 & 52 & 52 & 52 & 52 \\
3 & 0 & 0 & 0 & 23 & 29 & 29 & 29 & 29 & \color{orange}{52} & 52 & 52 & 52 & 52 & 52 & 72 & 72 \\
4 & 0 & 0 & 0 & 23 & 29 & 29 & 29 & 39 & 52 & 52 & 52 & 52 & \color{red}{\boxed{\color{currentColor}{68}}} & 68 & 72 & 72 \\
5 & 0 & 0 & 19 & 23 & 29 & 29 & 42 & 48 & 52 & 52 & 58 & 71 & 71 & 71 & 72 & \color{red}{\boxed{\color{lightgreen}{87}}} \\
\end{array}

$$

      **(d) $W = 17\text{ kg}$ – Optimal Val.: $K[5, 17] = 93$ ****– Selected: $[1, 2, 3, 5]$**

$$

\small\begin{array}{c|ccccccccccccccccc}
i \backslash w & 1 & 2 & 3 & 4 & 5 & 6 & 7 & 8 & 9 & 10 & 11 & 12 & 13 & 14 & 15 & 16 & 17 \\
\hline
1 & 0 & 0 & 0 & 0 & \color{red}{\boxed{\color{currentColor}{21}}} & 21 & 21 & 21 & 21 & 21 & 21 & 21 & 21 & 21 & 21 & 21 & 21 \\
2 & 0 & 0 & 23 & 23 & 23 & 23 & 23 & \color{red}{\boxed{\color{currentColor}{44}}} & 44 & 44 & 44 & 44 & 44 & 44 & 44 & 44 & 44 \\
3 & 0 & 0 & 23 & 23 & 30 & 30 & 30 & 53 & 53 & 53 & 53 & 53 & \color{red}{\boxed{\color{currentColor}{74}}} & 74 & 74 & 74 & 74 \\
4 & 0 & 0 & 23 & 23 & 30 & 30 & 30 & 53 & 53 & 53 & 53 & 53 & \color{orange}{74} & 74 & 74 & 74 & 74 \\
5 & 0 & 0 & 23 & 23 & 30 & 30 & 42 & 53 & 53 & 53 & 53 & 72 & 74 & 74 & 74 & 74 & \color{red}{\boxed{\color{lightgreen}{93}}} \\
\end{array}

$$

      **(e) $W = 17\text{ kg}$ – Optimal Val.: $K[5, 17] = 80$ ****– Selected: $[1, 2, 3, 5]$**

$$

\small\begin{array}{c|ccccccccccccccccc}
i \backslash w & 1 & 2 & 3 & 4 & 5 & 6 & 7 & 8 & 9 & 10 & 11 & 12 & 13 & 14 & 15 & 16 & 17 \\
\hline
1 & 0 & 0 & 0 & 0 & 17 & \color{red}{\boxed{\color{currentColor}{17}}} & 17 & 17 & 17 & 17 & 17 & 17 & 17 & 17 & 17 & 17 & 17 \\
2 & 0 & 0 & 0 & 23 & 23 & 23 & 23 & 23 & 40 & \color{red}{\boxed{\color{currentColor}{40}}} & 40 & 40 & 40 & 40 & 40 & 40 & 40 \\
3 & 0 & 0 & 16 & 23 & 23 & 23 & 39 & 39 & 40 & 40 & 40 & 56 & \color{red}{\boxed{\color{currentColor}{56}}} & 56 & 56 & 56 & 56 \\
4 & 0 & 0 & 16 & 23 & 23 & 23 & 39 & 39 & 40 & 40 & 40 & 56 & \color{orange}{56} & 56 & 56 & 56 & 72 \\
5 & 0 & 0 & 16 & 24 & 24 & 24 & 40 & 47 & 47 & 47 & 63 & 63 & 64 & 64 & 64 & 80 & \color{red}{\boxed{\color{lightgreen}{80}}} \\
\end{array}

$$

      **(f) $W = 17\text{ kg}$ – Optimal Val.: $K[5, 17] = 98$ ****– Selected: $[1, 3, 4, 5]$**

$$

\small\begin{array}{c|ccccccccccccccccc}
i \backslash w & 1 & 2 & 3 & 4 & 5 & 6 & 7 & 8 & 9 & 10 & 11 & 12 & 13 & 14 & 15 & 16 & 17 \\
\hline
1 & 0 & 0 & 0 & 26 & 26 & 26 & 26 & 26 & 26 & 26 & 26 & 26 & 26 & 26 & 26 & 26 & 26 \\
2 & 0 & 0 & 0 & 26 & 26 & 26 & 26 & 26 & 26 & 49 & 49 & 49 & 49 & 49 & 49 & 49 & 49 \\
3 & 0 & 0 & 0 & \color{orange}{28} & 28 & 28 & 28 & 54 & 54 & 54 & 54 & 54 & 54 & 77 & 77 & 77 & 77 \\
4 & 0 & 0 & 0 & 28 & 28 & 28 & 28 & 54 & 54 & 56 & 56 & 56 & 56 & \color{orange}{82} & 82 & 82 & 82 \\
5 & 0 & 0 & 16 & 28 & 28 & 28 & 44 & 54 & 54 & 56 & 70 & 70 & 72 & 82 & 82 & 82 & \color{lightgreen}{98} \\
\end{array}

$$
