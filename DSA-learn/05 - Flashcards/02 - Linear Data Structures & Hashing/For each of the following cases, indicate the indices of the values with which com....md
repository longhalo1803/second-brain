---
title: "For each of the following cases, indicate the indices of the values with which com..."
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
  - "For each of the following cases, indicate the indices of the values with which com..."
---

# 🎴 For each of the following cases, indicate the indices of the values with which com...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: 📝📍 For each of the following cases, indicate the indices of the values with which comparisons are made by the BinarySearch function:

1. $A = 2, 3, 4, 5, 6, 6, 6, 7, 7, 7, 8, 8, 8, 9$ and $key = 8$;

2. $A = 2, 3, 4, 5, 6, 6, 6, 6, 7, 7, 7, 7, 8, 8, 8, 9$ and $key = 8$;

3. $A = 2, 4, 7, 21, 22, 25, 27, 31, 33, 46, 67, 89$ and $key = 7$;

4. $A = 2, 4, 7, 21, 22, 25, 27, 31, 33, 46, 67, 89$ and $key = 90$;

5. $A = 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3$ and $key = 4$. #card
   ?
6. $A[6] = 6$ and $A[10] = 8$;
7. $A[7] = 6$, $A[11] = 7$ and $A[13] = 8$;
8. $A[5] = 25$ and $A[2] = 7$;
9. $A[5] = 25$, $A[8] = 33$, $A[10] = 67$ and $A[11] = 89$;
10. $A[9] = 3$, $A[14] = 3$, $A[16] = 3$, $A[17] = 3$, $A[18] = 3$.

📌 Solution for ex. 1 and 3:

$$
\begin{array}{c|c|c|c|c}
i & j & k & key \text{ vs } A[k] \\
\hline
0 & 13 & 6 & 8 > 6 \rightarrow\text{right} \\
6+1 & 13 & 10 & 8 = 8 \rightarrow\text{✅}
\end{array}
$$

$$
\begin{array}{c|c|c|c}
i & j & k & key \text{ vs } A[k] \\
\hline
0 & 11 & 5 & 7 https://coddy.tech/visualize/searching/binary-search
$$
