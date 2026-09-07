---
title: "How do you correctly calculate the index of the middle element k of an interval bo..."
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
  - "How do you correctly calculate the index of the middle element k of an interval bo..."
---

# 🎴 How do you correctly calculate the index of the middle element k of an interval bo...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: How do you correctly calculate the **index of the middle element $k$** of an interval bounded by indices $i$ and $j$?

$$
\begin{array}{c}
i \hspace{2.5cm} k \hspace{2.5cm} j \\[-0.1cm]
\color[RGB]{52, 152, 219}{\rule{6cm}{0.5cm}}
\end{array}
$$ #card
?
To get to $k$, you need to add half of the distance between $i$ and $j$ to the left/lower index $i$, then apply the __floor function__ ($\lfloor \dots \rfloor$):

$$

k = \left\lfloor i + \frac{j - i}{2} \right\rfloor = \left\lfloor \frac{2i + j - i}{2} \right\rfloor = \left\lfloor \frac{i + j}{2} \right\rfloor

$$

📝 **Example with an odd number of elements:**
Interval from index $3$ to $11$ (9 elements: $3, 4, 5, 6, \textcolor{red}{7}, 8, 9, 10, 11$):

$$

k = \left\lfloor \frac{3 + 11}{2} \right\rfloor = 7

$$

📝 **Example with an even number of elements:**
Interval from index $3$ to $12$ (10 elements: $3, 4, 5, 6, \textcolor{red}7, 8, 9, 10, 11, 12$):

$$

k = \left\lfloor \frac{3 + 12}{2} \right\rfloor = \lfloor 7.5 \rfloor = 7

$$
$$
