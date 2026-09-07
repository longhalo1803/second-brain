---
title: "📘 Exercise 3.2"
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
  - "📘 Exercise 3.2"
---

# 🎴 📘 Exercise 3.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 3.2

**Input:** A binary tree $T$ implemented with nodes and pointers (fields $val, left, right$), and a pointer $t$ to a node.
**Output:** The level of node $t$ in $T$ (root is at level 0), or $-1$ if $t$ is not in $T$.

- Show an example of input and output.
- Explain a recursive algorithm indicating base and recursive cases.
- Provide the pseudocode.
- Analyze the computational complexity.
- Using this solution, write pseudocode to determine whether two given nodes $t_1$ and $t_2$ are cousins (two nodes are cousins if they are at the same level but have different parents). #card
  ?
  **Reasoning:**
  A recursive DFS tracking the current depth level returns the depth when node $t$ is found. For cousins, we check that their levels are identical and $\ge 2$, and that their parent nodes are distinct.

**1. Example:**
In a tree with root $r$ (level 0), left child $a$ (level 1), and right child of $a$ as $t$, the level is 2. If $t \notin T$, output is $-1$.

**2. Recursive Strategy:**

- _Base Case:_ If $u = \text{NIL}$, return $-1$. If $u = t$, return current level $l$.
- _Recursive Case:_ Call recursively on $u.left$ with level $l + 1$. If the result is not $-1$, return it; otherwise, return the call on $u.right$ with level $l + 1$.
  **3. Pseudocode:**

```text
Function GetLevel(u, t, l):
    if u = NIL then return -1
    if u = t then return l
    left_res ≤ftarrow GetLevel(u.left, t, l + 1)
    if left_res ≠ -1 then return left_res
    return GetLevel(u.right, t, l + 1)

Algorithm FindLevel(T, t):
    return GetLevel(T, t, 0)
```

**4. Complexity:**

- Time Complexity: $O(n)$, visiting each node at most once.
- Space Complexity: $O(h)$ auxiliary recursion stack space.
  **5. Cousins Check Pseudocode:**

```text
Function GetParent(u, target):
    if u = NIL u = target then return NIL
    if u.left = target u.right = target then return u
    p ≤ftarrow GetParent(u.left, target)
    if p ≠ NIL then return p
    return GetParent(u.right, target)

Algorithm AreCousins(T, t_1, t_2):
    l_1 ≤ftarrow FindLevel(T, t_1); \; l_2 ≤ftarrow FindLevel(T, t_2)
    if l_1 ≠ l_2 l_1 ≤ 0 then return FALSE
    p_1 ≤ftarrow GetParent(T, t_1); \; p_2 ≤ftarrow GetParent(T, t_2)
    return (p_1 ≠ NIL p_2 ≠ NIL p_1 ≠ p_2)
```
