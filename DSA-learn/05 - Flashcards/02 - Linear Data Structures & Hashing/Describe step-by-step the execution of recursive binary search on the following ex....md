---
title: "Describe step-by-step the execution of recursive binary search on the following ex..."
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
  - "Describe step-by-step the execution of recursive binary search on the following ex..."
---

# 🎴 Describe step-by-step the execution of recursive binary search on the following ex...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: Describe step-by-step the execution of recursive binary search on the following example array:

L = with key = 23. Then try with key = 24.

````text
BinarySearch(L, i, j, key)
    if j - i < 0 then
        return -1
    else
        k := floor((i + j) / 2)
        if key = L[k] then
            return k
        if key < L[k] then
            return BinarySearch(L, i, k-1, key)
        else
            return BinarySearch(L, k+1, j, key)
``` #card
?
$$
L = \langle \overset{0}{1}, \overset{1}{2}, \overset{2}{5}, \overset{3}{10}, \overset{4}{11}, \overset{5}{14}, \overset{6}{17}, \overset{7}{23}, \overset{8}{24}, \overset{9}{30} \rangle
$$

The array has indices from $0$ to $9$ ($n = 10$). Searching for $key = 23$:

1. **First call (main):** $\textsf{BinarySearch(L, 0, 9, 23)}$
- $i = 0$, $j = 9$ $\implies j - i = 9 \ge 0$
- $k = \Big\lfloor \frac{0 + 9}{2} \Big\rfloor = 4$
- $L[4] = 11$. Since $11 < 23$ ($L[k] < key$), the first call is *suspended* and it proceeds to the second call.

2. **Second call:** $\textsf{BinarySearch(L, 5, 9, 23)}$
- $i = 5$, $j = 9$ $\implies j - i = 4 \ge 0$
- $k = \Big\lfloor \frac{5 + 9}{2} \Big\rfloor = 7$
- $L[7] = 23$. Since $23 = 23$ ($L[k] = key$), the call directly returns index $7$.

The main call resumes, propagates the output, and the algorithm terminates returning $7$.
______________________
Now searching for $key = 24$. The following recursive steps occur:

$$
\begin{array}{c|c|c|c|lc}
\text{Call #} & i & j & k & \text{return} & \;\;8 \\ \hline
1 & 0 & 9 & 4 & ? \ \small\color{gray} \nearrow 8 & \;\;\uparrow \\
2 & 5 & 9 & 7 & ? \ \small\color{gray} \nearrow 8 & \;\;\uparrow \\
3 & 8 & 9 & 8 & 8 & \nearrow
\end{array}
$$
````
