---
title: "Prove the Rank Proposition by induction."
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
  - "Prove the Rank Proposition by induction."
---

# 🎴 Prove the Rank Proposition by induction.

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: Prove the Rank Proposition by induction. #card

?
The proof proceeds by induction on the number $t$ of `Union` operations performed.

**Base Case ($t = 0$)**:
• Immediately after executing `Make-set(X)` (before performing any `Union` operation):

1. Every tree in the forest has exactly **1 node** ($k = 1$).
2. For every root $r$, the initial rank assigned is $\textsf{rank}[r] = 0$.

Checking the inequality:

```text
2^{rank[r]} = 2^0 = 1 ≤ 1 = k
```

The property $2^{\textsf{rank}[r]} \le k$ therefore holds trivially and exactly for each tree.

**Inductive Hypothesis**: After $t \ge 0$ `Union` operations, for any tree of $k \le n$ nodes with representative (root) $r$, it holds that $2^{\textsf{rank}[r]} \le k$.

**Inductive Step ($t+1$)**: Consider an operation `Union(DS, x, y)`. Let $xr = \textsf{Find-set}(x)$ and $yr = \textsf{Find-set}(y)$ with associated sets $S_x$ and $S_y$, respectively. If $xr = yr$, the statement remains trivially true.

If $xr \neq yr$:

• **Case 1 ($\textsf{rank}[xr] > \textsf{rank}[yr]$)**:
$xr$ becomes the new root of the union and its rank does not change ($\textsf{rank}'[xr] = \textsf{rank}[xr]$). Since the sets are disjoint ($S_x \cap S_y = \emptyset$):

```text
|S_x S_y| = |S_x| + |S_y| > |S_x| ≥ 2^{rank[xr]}
```

Thus, the number of nodes in the new tree satisfies $|S_x \cup S_y| \ge 2^{\textsf{rank}'[xr]}$.

• **Case 2 ($\textsf{rank}[xr] < \textsf{rank}[yr]$)**:
Symmetric to Case 1, with $yr$ becoming the new root while keeping its rank unchanged.

• **Case 3 ($\textsf{rank}[xr] = \textsf{rank}[yr]$)**:

Let $xr$ and $yr$ be the roots of the two disjoint sets $S_x$ and $S_y$. When the ranks are equal, the algorithm sets $yr$ as the new root and increments its rank by 1:

```text
rank'[yr] = rank[yr] + 1
```

Since the sets are disjoint ($S_x \cap S_y = \emptyset$), the cardinality of the new union set satisfies:

```text
{aligned}|S_x S_y|                   // = |S_x| + |S_y|
    // ≥ 2^{rank[xr]} + 2^{rank[yr]} (by inductive hypothesis)
    // = 2^{rank[yr]} + 2^{rank[yr]} (since rank[xr] = rank[yr])
// = 2 2^{rank[yr]}
// = 2^{rank[yr] + 1} = 2^{rank'[yr]}{aligned}
```

Thus, the resulting tree rooted at $yr$ has at least $2^{\textsf{rank}'[yr]}$ nodes, completing the inductive proof.
