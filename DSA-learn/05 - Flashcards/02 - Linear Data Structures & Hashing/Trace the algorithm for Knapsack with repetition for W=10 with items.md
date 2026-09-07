---
title: "Trace the algorithm for Knapsack with repetition for W=10 with items"
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
  - "Trace the algorithm for Knapsack with repetition for W=10 with items"
---

# 🎴 Trace the algorithm for Knapsack with repetition for W=10 with items

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: Trace the algorithm for Knapsack with repetition for $W=10$ with items:

Item 1 ($w=6, v=30$),
Item 2 ($w=3, v=14$),
Item 3 ($w=4, v=16$),
Item 4 ($w=2, v=9$). #card
?
**Data:** $\min w_i = 2$. For $w < 2$, $K[w] = 0$.

Formula: $\textsf{K}\texttt{[}\textsf{w}\texttt{]} \textsf{ := } \max_{i : w_i \le \textsf{w}} \{ v_i + \textsf{K}\texttt{[}\textsf{w} - w_i\texttt{]} \}$

**Computation of **$K[w]$**:**

$$

\begin{array}{|c|c|c|c|c|c|c|c|c|c|c|c|}
\hline
w & 0 & 1 & 2 & 3 & 4 & 5 & 6 & 7 & 8 & 9 & 10 \\
\hline
K[w] & 0 & 0 & 9 & 14 & 18 & 23 & 30 & 32 & 39 & 44 & 48 \\
\hline
\color{gray}\text{Item} & \color{gray}- & \color{gray}- & \color{gray}4 & \color{gray}2 & \color{gray}4 & \color{gray}\text{2 or 4} & \color{gray}1 & \color{gray}\text{2 or 4} & \color{gray}\text{1 or 4} & \color{gray}\text{1 or 2} & \color{gray}\text{1 or 4} \\
\hline
\end{array}

$$

(📌 Note: the _Item_ row is only necessary if you want to backtrack the elements that led to the maximum value, since the algorithm does not need to know which items were used in previous steps to compute $K[w]$; knowing the numerical value $K[w - w_i]$ is sufficient. It is shown here only to help follow the calculations, perform the final backtracking quickly, and understand how the process works.)

- $w=0,1$: No item fits within the weight limit ($w < 2$) $\implies K[w] = 0$.
- $w=2$: cand. $\{4\} \implies v_4 + K[0] = 9 + 0 = 9$ $\rightarrow K[2]=9$, item $= 4$
- $w=3$: cand. $\{2, 4\}$:
  $i=2: 14 + K[0] = 14$;
  $i=4: 9 + K[1] = 9 \implies K[3]=14$, item $= 2$
- $w=4$: cand. $\{2, 3, 4\}$:
  $i=2: 14 + K[1] = 14$;
  $i=3: 16 + K[0] = 16$;
  $i=4: 9 + K[2] = 18 \implies K[4]=18$, item $= 4$
- $w=5$: cand. $\{2, 3, 4\}$:
  $i=2: 14 + K[2] = 23$;
  $i=3: 16 + K[1] = 16$;
  $i=4: 9 + K[3] = 23 \implies K[5]=23$, item $= 2$
- $w=6$: cand. $\{1, 2, 3, 4\}$:
  $i=1: 30 + K[0] = 30$;
  $i=2: 14 + K[3] = 28$;
  $i=3: 16 + K[2] = 25$;
  $i=4: 9 + K[4] = 27 \implies K[6]=30$, item $= 1$
- $w=7$: cand. $\{1, 2, 3, 4\}$:
  $i=1: 30 + K[1] = 30$;
  $i=2: 14 + K[4] = 32$;
  $i=4: 9 + K[5] = 32 \implies K[7]=32$, item $= 2$
- $w=8$: cand. $\{1, 2, 3, 4\}$:
  $i=1: 30 + K[2] = 39$;
  $i=4: 9 + K[6] = 39 \implies K[8]=39$, item $= 4$
- $w=9$: cand. $\{1, 2, 3, 4\}$:
  $i=1: 30 + K[3] = 44$;
  $i=2: 14 + K[6] = 44 \implies K[9]=44$, item $= 1$
- $w=10$: cand. $\{1, 2, 3, 4\}$:
  $i=1: 30 + K[4] = 48$;
  $i=4: 9 + K[8] = 48 \implies K[10]=48$, item $= 1$

**Optimal solution:**
Maximum value = **48**.
**Backtracking from 10** (there are multiple optimal solutions, one of them is shown below):
_Using the Item row_: start at W and directly follow the indicated indices, subtracting each time the weight of the chosen item:

$$

10 \xrightarrow{\text{Item 1}} 4
\xrightarrow{\text{Item 4}} 2
\xrightarrow{\text{Item 4}} 0

$$

_Without using the Item row_: at each $w$, search for an item $i$ for which

$$

K[w]=v_i+K[w-w_i]

$$

If one is found, that item belongs to the solution; set $w=w-w_i$ and repeat.
If there are multiple, there are multiple optimal choices.
item 1 ($w=6$) $\rightarrow$ remaining 4 $\rightarrow$ item 4 ($w=2$) $\rightarrow$ remaining 2 $\rightarrow$ item 4 ($w=2$) $\rightarrow$ remaining 0.

$$

\begin{aligned}
K[10]&=30+K[4] &&\Rightarrow \text{Item 1}\\
K[4]&=9+K[2] &&\Rightarrow \text{Item 4}\\
K[2]&=9+K[0] &&\Rightarrow \text{Item 4}\\
K[0]&=0 &&\Rightarrow \text{done}
\end{aligned}

$$

**Selection**:
**Item 1 + Item 4 + Item 4** (total weight: 10).
