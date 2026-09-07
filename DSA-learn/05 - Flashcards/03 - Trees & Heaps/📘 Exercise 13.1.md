---
title: "📘 Exercise 13.1"
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
  - "📘 Exercise 13.1"
---

# 🎴 📘 Exercise 13.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 13.1

A _SumTree_ is a binary tree storing numeric keys where the key of every internal node $v$ equals the sum of the keys of all other nodes in the subtree rooted at $v$.

**Input:** A binary tree $T$ (fields: $left, right, key$) storing strictly positive integers ($> 0$).
**Output:** TRUE if $T$ is a SumTree, FALSE otherwise.

- Show two examples of height at least 3: one that is a SumTree and one that is not.
- Describe an algorithm to solve the problem and provide its pseudocode.
- Analyze the computational complexity. #card
  ?
  **Reasoning:**
  In a SumTree, for any internal node $v$, $v.key = \sum_{u \in Subtree(v), u \ne v} u.key$. This implies the total sum of all keys in $Subtree(v)$ is $v.key + v.key = 2 \cdot v.key$. A post-order traversal can return the total subtree sum while validating the property.

**1. Examples:**

- _SumTree:_ Root key $26$. Left child key $10$ (with leaves $4$ and $6$, sum $= 10$). Right child key $3$ (leaf $3$). Total non-root keys $= 10 + 4 + 6 + 3 + 3 = 26$. Valid.
- _Non-SumTree:_ Same structure with root key $25 \ne 26$. Invalid.
  **2. Algorithm Description:**
  Use a recursive function returning $(is\_sum\_tree, total\_sum)$. For an empty tree, return $(\text{true}, 0)$. For a leaf, return $(\text{true}, leaf.key)$. For an internal node, recursively evaluate children; the node is valid if both subtrees are valid and $u.key = sum_{left} + sum_{right}$. The total sum returned is $u.key + sum_{left} + sum_{right}$.

**3. Pseudocode:**

```text
Function CheckSumTree(u):
    if u = NIL then return (true, 0)
    if u.left = NIL u.right = NIL then return (true, u.key)
    (ok_L, s_L) ≤ftarrow CheckSumTree(u.left)
    (ok_R, s_R) ≤ftarrow CheckSumTree(u.right)
    if not ok_L not ok_R (u.key ≠ s_L + s_R) then
        return (false, 0)
    return (true, u.key + s_L + s_R)

Algorithm IsSumTree(T):
    (ok, sum) ≤ftarrow CheckSumTree(T)
    return ok
```

**4. Complexity:**
$\Theta(n)$ time, visiting each node once, and $O(h)$ auxiliary stack space.
