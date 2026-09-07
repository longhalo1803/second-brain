---
title: "Exercise 3 - Knapsack with Repetition (Unbounded Knapsack)"
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
  - "Exercise 3 - Knapsack with Repetition (Unbounded Knapsack)"
---

# 🎴 Exercise 3 - Knapsack with Repetition (Unbounded Knapsack)

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: 📝📍 Exercise 3 - Knapsack with Repetition (Unbounded Knapsack)

Given the item types described in the tables below and a knapsack of capacity $W = 15\text{ kg}$, determine, for each case, the optimal knapsack filling under the assumption that multiple items of each type can be chosen (knapsack with repetitions).

**(a)**ItemWeight (kg)Value (€)15.015.025.026.034.025.046.028.056.016.0**(b)**ItemWeight (kg)Value (€)15.027.026.029.036.023.044.027.055.018.0**(c)**ItemWeight (kg)Value (€)14.017.026.020.036.028.044.020.055.021.0**(d)**ItemWeight (kg)Value (€)15.021.026.026.036.020.045.016.054.019.0**(e)**ItemWeight (kg)Value (€)15.015.024.017.033.021.045.029.053.028.0**(f)**ItemWeight (kg)Value (€)15.024.026.020.034.024.046.025.055.015.0**(g)**ItemWeight (kg)Value (€)16.023.024.021.034.026.045.028.053.024.0 #card
?
📌 Note:
In the version **with repetition**, there is no need to build a 2D table (Items × Weight) as in 0-1 knapsack: a one-dimensional array $K[w]$ for remaining capacities from $0$ to $W$ is sufficient.
However, for the purpose of the exercise, it is helpful to also write a row for $w$ and one for $\text{Item}$ to aid the steps.

Applying the dynamic programming formula:

$$

K[w] = \max\_{i : w_i \le w} \{ v_i + K[w - w_i] \}

$$

**How to trace back the chosen items (_backtracking_):**
• **With the Item row (auxiliary array $\text{item}[w]$ or **$\text{choice}[w]$**):** Directly stores the last item $i$ inserted for capacity $w$. Reconstruction is immediate: read $i = \text{item}[w]$ and decrement the remaining capacity $w \leftarrow w - w_i$ until $w = 0$.
• **Without the Item row:** The auxiliary array is not strictly necessary. Backtracking can be performed after the fact starting from $w = W$ and checking for each weight which item $i$ satisfies the equality $K[w] = v_i + K[w - w_i]$.

    **(a)**

$$

\begin{array}{|c|c|c|c|c|c|c|c|c|c|c|c|c|c|c|c|c|}
\hline
w & 0 & 1 & 2 & 3 & 4 & 5 & 6 & 7 & 8 & 9 & 10 & 11 & 12 & 13 & 14 & 15 \\
\hline
K[w] & 0 & 0 & 0 & 0 & 25 & 26 & 28 & 28 & 50 & 51 & 53 & 54 & 75 & 76 & 78 & 79 \\
\hline
\text{Item} & - & - & - & - & 3 & 2 & 4 & 4 & 3 & 2, 3 & 3, 4 & 2, 4 & 3 & 2, 3 & 3, 4 & 2, 3, 4 \\
\hline
\end{array}

$$

**Optimal solution:** Item 2 + Item 3 + Item 4 (Weight: $15\text{ kg}$, Value: $79\text{ €}$)

    **(b)**

$$

\begin{array}{|c|c|c|c|c|c|c|c|c|c|c|c|c|c|c|c|c|}
\hline
w & 0 & 1 & 2 & 3 & 4 & 5 & 6 & 7 & 8 & 9 & 10 & 11 & 12 & 13 & 14 & 15 \\
\hline
K[w] & 0 & 0 & 0 & 0 & 27 & 27 & 29 & 27 & 54 & 54 & 56 & 56 & 81 & 81 & 83 & 83 \\
\hline
\text{Item} & - & - & - & - & 4 & 1 & 2 & 1, 4 & 4 & 1, 4 & 2, 4 & 1, 2 & 4 & 1, 4 & 2, 4 & 1, 2, 4 \\
\hline
\end{array}

$$

**Optimal solution:** Item 1 + Item 2 + Item 4 (Weight: $15\text{ kg}$, Value: $83\text{ €}$)

    **(c)**

$$

\begin{array}{|c|c|c|c|c|c|c|c|c|c|c|c|c|c|c|c|c|}
\hline
w & 0 & 1 & 2 & 3 & 4 & 5 & 6 & 7 & 8 & 9 & 10 & 11 & 12 & 13 & 14 & 15 \\
\hline
K[w] & 0 & 0 & 0 & 0 & 20 & 21 & 28 & 21 & 40 & 41 & 48 & 49 & 60 & 61 & 68 & 69 \\
\hline
\text{Item} & - & - & - & - & 4 & 5 & 3 & 5 & 4 & 4, 5 & 3, 4 & 3, 5 & 4 & 4, 5 & 3, 4 & 3, 4, 5 \\
\hline
\end{array}

$$

**Optimal solution:** Item 3 + Item 4 + Item 5 (Weight: $15\text{ kg}$, Value: $69\text{ €}$)

    **(d)**

$$

\begin{array}{|c|c|c|c|c|c|c|c|c|c|c|c|c|c|c|c|c|}
\hline
w & 0 & 1 & 2 & 3 & 4 & 5 & 6 & 7 & 8 & 9 & 10 & 11 & 12 & 13 & 14 & 15 \\
\hline
K[w] & 0 & 0 & 0 & 0 & 19 & 21 & 26 & 21 & 38 & 40 & 45 & 47 & 57 & 59 & 64 & 66 \\
\hline
\text{Item} & - & - & - & - & 5 & 1 & 2 & 1 & 5 & 1, 5 & 2, 5 & 1, 2 & 5 & 1, 5 & 2, 5 & 1, 2, 5 \\
\hline
\end{array}

$$

**Optimal solution:** Item 1 + Item 2 + Item 5 (Weight: $15\text{ kg}$, Value: $66\text{ €}$)

    **(e)**

$$

\begin{array}{|c|c|c|c|c|c|c|c|c|c|c|c|c|c|c|c|c|}
\hline
w & 0 & 1 & 2 & 3 & 4 & 5 & 6 & 7 & 8 & 9 & 10 & 11 & 12 & 13 & 14 & 15 \\
\hline
K[w] & 0 & 0 & 0 & 28 & 28 & 29 & 56 & 56 & 57 & 84 & 84 & 85 & 112 & 112 & 113 & 140 \\
\hline
\text{Item} & - & - & - & 5 & 5 & 4 & 5 & 5 & 4, 5 & 5 & 5 & 4, 5 & 5 & 5 & 4, 5 & 5 \\
\hline
\end{array}

$$

**Optimal solution:** 5× Item 5 (Weight: $15\text{ kg}$, Value: $140\text{ €}$)

    **(f)**

$$

\begin{array}{|c|c|c|c|c|c|c|c|c|c|c|c|c|c|c|c|c|}
\hline
w & 0 & 1 & 2 & 3 & 4 & 5 & 6 & 7 & 8 & 9 & 10 & 11 & 12 & 13 & 14 & 15 \\
\hline
K[w] & 0 & 0 & 0 & 0 & 24 & 24 & 25 & 24 & 48 & 48 & 49 & 49 & 72 & 72 & 73 & 73 \\
\hline
\text{Item} & - & - & - & - & 3 & 1, 3 & 4 & 3 & 3 & 1, 3 & 3, 4 & 1 & 3 & 1, 3 & 3, 4 & 1, 3, 4 \\
\hline
\end{array}

$$

**Optimal solution:** Item 1 + Item 3 + Item 4 (Weight: $15\text{ kg}$, Value: $73\text{ €}$)

    **(g)**

$$

\begin{array}{|c|c|c|c|c|c|c|c|c|c|c|c|c|c|c|c|c|}
\hline
w & 0 & 1 & 2 & 3 & 4 & 5 & 6 & 7 & 8 & 9 & 10 & 11 & 12 & 13 & 14 & 15 \\
\hline
K[w] & 0 & 0 & 0 & 24 & 26 & 28 & 48 & 50 & 52 & 72 & 74 & 76 & 96 & 98 & 100 & 120 \\
\hline
\text{Item} & - & - & - & 5 & 3 & 4 & 5 & 3, 5 & 3, 4, 5 & 5 & 3, 5 & 3, 4, 5 & 5 & 3, 5 & 3, 4, 5 & 5 \\
\hline
\end{array}

$$

**Optimal solution:** 5× Item 5 (Weight: $15\text{ kg}$, Value: $120\text{ €}$)
