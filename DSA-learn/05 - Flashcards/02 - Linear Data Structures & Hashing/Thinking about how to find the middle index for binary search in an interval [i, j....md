---
title: "Thinking about how to find the middle index for binary search in an interval [i, j..."
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
  - "Thinking about how to find the middle index for binary search in an interval [i, j..."
---

# 🎴 Thinking about how to find the middle index for binary search in an interval [i, j...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: Thinking about how to find the middle index for binary search in an interval $[i, j]$, why is the formula $k = \frac{j-i}{2}$ wrong? Show an example.

$$
\begin{array}{c}
i \hspace{2.5cm} k \hspace{2.5cm} j \\[-0.1cm]
\color[RGB]{52, 152, 219}{\rule{6cm}{0.5cm}}
\end{array}
$$ #card
?
Because this calculation finds *half of the distance* between the two indices, not the absolute position of the median value within the array.

⚠️ **Problems:**
1. The value obtained does not necessarily fall within the interval $[i, j]$.
2. The value might not be an integer.

📝 **Example:**
Let $i = 100$ and $j = 109$:

$$

k = \frac{109 - 100}{2} = \frac{9}{2} = 4.5

$$

The value $4.5$ is not an integer and does not belong to the interval $[100, 109]$ at all.
$$
