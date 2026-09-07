---
title: "📘 Exercise 11.1"
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
  - "📘 Exercise 11.1"
---

# 🎴 📘 Exercise 11.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 11.1

**Input:** A binary tree $T$ with $n$ nodes (fields $key, left, right$) storing integer values.
**Output:** Modify $T$ so that all negative keys are pushed toward the bottom of the tree, without altering the structural topology of the tree (a node with a negative key cannot have any child with a non-negative key).

- Show an example with a tree of at least 7 nodes.
- Describe a recursive algorithm and provide its pseudocode.
- Analyze its computational complexity. #card
  ?
  **Reasoning:**
  This is analogous to a max-heap property between non-negative and negative numbers. A post-order traversal ensures that subtrees are valid, and whenever a node contains a negative key while a child has a non-negative key, we swap keys with the child and propagate the negative key downwards (push-down).

**1. Example:**
Root has key $-5$, left child has $10$, right child has $20$. Since root is negative and children are non-negative, $-5$ is swapped with $20$. Subtrees are processed recursively so all negative keys end up at leaf/bottom positions.

**2. Algorithm Description:**
First recursively fix the left and right subtrees. Then, apply a `PushDown` procedure: if the current node $u$ has a negative key, identify its child with the largest key. If that child has a non-negative key, swap keys with $u$ and recursively call `PushDown` on that child.

**3. Pseudocode:**

```text
Procedure PushDown(u):
    if u = NIL (u.left = NIL u.right = NIL) then return
    if u.key < 0 then
        target ≤ftarrow NIL
        if u.left ≠ NIL u.right ≠ NIL then
            target ≤ftarrow (u.left.key ≥ u.right.key \,?\, u.left : u.right)
        else if u.left ≠ NIL then target ≤ftarrow u.left
        else target ≤ftarrow u.right
        if target.key ≥ 0 then
            swap(u.key, target.key)
            PushDown(target)

Algorithm ShiftNegativesDown(u):
    if u = NIL then return
    ShiftNegativesDown(u.left)
    ShiftNegativesDown(u.right)
    PushDown(u)
```

**4. Complexity:**

- Time Complexity: Analogous to Build-Heap, pushing down a node of height $h$ takes $O(h)$. The sum of heights across all nodes is $O(n)$.
- Space Complexity: $O(h)$ auxiliary recursion stack space.
