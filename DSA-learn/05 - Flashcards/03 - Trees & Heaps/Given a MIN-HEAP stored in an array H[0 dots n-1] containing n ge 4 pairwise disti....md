---
title: "Given a MIN-HEAP stored in an array H[0 dots n-1] containing n ge 4 pairwise disti..."
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
  - "Given a MIN-HEAP stored in an array H[0 dots n-1] containing n ge 4 pairwise disti..."
---

# 🎴 Given a MIN-HEAP stored in an array H[0 dots n-1] containing n ge 4 pairwise disti...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: ❓ Given a MIN-HEAP stored in an array $H[0 \dots n-1]$ containing $n \ge 4$ pairwise distinct integer keys...

- in which positions of $H$ can the second smallest element appear?
- for $k = 3, 4$, in which positions of $H$ can the $k$-th smallest element appear?
- in which positions of $H$ can the maximum element appear? #card
  ?
- **Second smallest element ($k=2$):**
  In a min-heap, the fundamental heap property dictates that the key of every node is less than or equal to that of its children. Because the keys are distinct, the absolute minimum element must reside at the root at index $0$. The second smallest element must necessarily be one of the immediate children of the root:

$$

\text{Possible positions: } \{1, 2\}

$$

- **$k$-th smallest element for $k=3, 4$:**
  An element cannot have more than $k-1$ ancestors that are strictly smaller than itself. Consequently, the $k$-th smallest element can be at depth at most $k-1$ (where the root is at depth $0$).
- **For $k=3$:** It can reside at depth $1$ (the other child of the root that is not the second minimum) or at depth $2$ (a child of the second minimum).
  Depth $1$: indices $\{1, 2\}$.
  Depth $2$: children indices of $1$ and $2$, namely $\{3, 4, 5, 6\}$ (assuming $n$ is large enough; here $n \ge 4$).

$$

\text{Possible positions for } k=3: \{1, 2, 3, \dots, \min(6, n-1)\}

$$

- **For $k=4$:** It can reside at depth $1$, $2$, or $3$ (child of a node at depth $2$).
  Depth $3$: indices from $2 \cdot 3 + 1 = 7$ to $2 \cdot 6 + 2 = 14$.

$$

\text{Possible positions for } k=4: \{1, 2, 3, \dots, \min(14, n-1)\}

$$

- **Maximum element:**
  By virtue of the min-heap property, the maximum element cannot be the parent of any node; otherwise, it would violate the condition $H[\text{parent}] < H[\text{child}]$. Therefore, it must necessarily be located in a **leaf**.
  In a 0-indexed representation from $0$ to $n-1$, internal nodes occupy indices from $0$ to $\lfloor \frac{n}{2} \rfloor - 1$.
  Consequently, leaves occupy positions:

$$

\text{Possible positions for the maximum: } \left\{\left\lfloor \frac{n}{2} \right\rfloor, \dots, n-1\right\}

$$
