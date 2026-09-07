---
title: "📘 Exercise 25.1"
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
  - "📘 Exercise 25.1"
---

# 🎴 📘 Exercise 25.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 25.1

**Input:** A binary tree $T$ implemented with nodes and pointers (fields: $val, left, right$) storing integers, and two integers $k_1, k_2$ such that $k_2 \ge k_1 \ge 0$.
**Output:** The sum of all values stored in nodes that lie between level $k_1$ and level $k_2$ inclusive (root is at level 0).

- Show a significant example.
- Describe the algorithm in words.
- Provide pseudocode.
- Analyze computational complexity. #card
  ?
  **Reasoning:**
  Traverse the tree passing the current level. If the current level is $\le k_2$, explore children. If the current level falls in $[k_1, k_2]$, accumulate the node's value into the sum.

**1. Example:**
Tree with root at level 0 (val 10), children at level 1 (vals 5, 15), grandchildren at level 2 (vals 1, 2, 3, 4). Let $k_1 = 1, k_2 = 2$.
Nodes at levels 1 and 2: $5 + 15 + 1 + 2 + 3 + 4 = 30$. Output: 30.

**2. Algorithm Description:**
Recursively traverse the tree. If the current node is NIL or its level exceeds $k_2$, return 0. Otherwise, recursively sum the results of the left and right subtrees at $level + 1$, adding $u.val$ if $level \ge k_1$.

**3. Pseudocode:**

```text
Function SumLevelsRec(u, level, k_1, k_2):
    if u = NIL level > k_2 then return 0
    current ≤ftarrow (level ≥ k_1 \,?\, u.val : 0)
    left_sum ≤ftarrow SumLevelsRec(u.left, level + 1, k_1, k_2)
    right_sum ≤ftarrow SumLevelsRec(u.right, level + 1, k_1, k_2)
    return current + left_sum + right_sum

Algorithm SumLevels(T, k_1, k_2):
    return SumLevelsRec(T, 0, k_1, k_2)
```

**4. Complexity:**
Visits each node at level $\le k_2 + 1$ at most once: $O(n)$ time and $O(h)$ auxiliary stack space.
