---
title: "📘 Exercise 28.1"
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
  - "📘 Exercise 28.1"
---

# 🎴 📘 Exercise 28.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 28.1

**Input:** A binary tree $T$ implemented with nodes and pointers (fields $val, left, right$) storing integer values.
**Output:** Modify $T$ by adding a new right child to every leaf, whose value is the sum of the keys along the path from the root to that leaf.

- Show an example with at least 6 leaves.
- Describe a recursive algorithm stating base and recursive cases.
- Provide pseudocode.
- Analyze computational complexity. #card
  ?
  **Reasoning:**
  Traverse the tree passing the running sum of keys from the root down to the current node. When a leaf is reached, allocate a new node with key equal to $running\_sum + leaf.val$ and attach it as the leaf's right child.

**Pseudocode:**

```text
Procedure AugmentLeaves(u, current_sum):
    if u = NIL then return
    new_sum ≤ftarrow current_sum + u.val
    if u.left = NIL u.right = NIL then
        new_node ≤ftarrow new TreeNode(new_sum)
        u.right ≤ftarrow new_node
        return
    AugmentLeaves(u.left, new_sum)
    AugmentLeaves(u.right, new_sum)

Algorithm AddPathSumLeaves(T):
    AugmentLeaves(T, 0)
```

**Complexity:**
Each original node is visited once: $\Theta(n)$ time and $O(h)$ auxiliary stack space.
