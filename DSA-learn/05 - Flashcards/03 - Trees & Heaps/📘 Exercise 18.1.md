---
title: "📘 Exercise 18.1"
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
  - "📘 Exercise 18.1"
---

# 🎴 📘 Exercise 18.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 18.1

**Input:** A binary tree $T$ (fields: $left, right, key$ storing natural numbers).
**Output:** For every node $u \in T$, print the average of the values contained in the subtree rooted at $u$ (including $u$).

- Provide an example on a tree of height at least 3.
- Write recursive pseudocode WITHOUT using global variables.
- Analyze the computational complexity. #card
  ?
  **Reasoning:**
  To compute the average of a subtree, we need the sum of all keys and the total number of nodes in that subtree. A post-order traversal computes $(sum, count)$ bottom-up from children, computes $average = sum / count$, prints it, and returns the pair to the parent.

**1. Example:**
Root $A(10)$ with left child $B(6)$ and right child $C(8)$. $B$ has left leaf $D(2)$ and right leaf $E(4)$.
Subtree averages: $D: 2/1 = 2.0$; $E: 4/1 = 4.0$; $B: (6+2+4)/3 = 4.0$; $C: 8/1 = 8.0$; $A: (10+12+8)/5 = 6.0$.

**2. Pseudocode:**

```text
Function PostOrderAverage(u):
    if u = NIL then return (0, 0)
    (sum_L, cnt_L) ≤ftarrow PostOrderAverage(u.left)
    (sum_R, cnt_R) ≤ftarrow PostOrderAverage(u.right)
    total_sum ≤ftarrow u.key + sum_L + sum_R
    total_cnt ≤ftarrow 1 + cnt_L + cnt_R
    avg ≤ftarrow total_sum / total_cnt
    print ("Node ", u.key, " Average: ", avg)
    return (total_sum, total_cnt)

Algorithm PrintSubtreeAverages(T):
    PostOrderAverage(T)
```

**3. Complexity:**
Each node is visited once: $\Theta(n)$ time and $O(h)$ auxiliary recursion stack space.
