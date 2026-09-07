---
title: "📘 Exercise 5.1"
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
  - "📘 Exercise 5.1"
---

# 🎴 📘 Exercise 5.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 5.1

**Input:** A binary tree $T$ implemented with nodes and pointers (fields $val, left, right$, without parent pointers).
**Output:** TRUE if $T$ is full (every node has either 0 or 2 children), FALSE otherwise.

- Describe a recursive algorithm indicating base and recursive cases.
- Provide the pseudocode.
- Analyze the computational complexity, presenting best and worst cases.
- Explain how to modify the procedure to test whether $T$ is also perfectly balanced (all leaves at the same depth). #card
  ?
  **Reasoning:**
  A node violates the full tree property if it has exactly one child. Recursively verify that every node has either 0 or 2 children and that both subtrees are full.

**1. Recursive Strategy:**

- _Base Case:_ If $u = \text{NIL}$, return TRUE. If $u$ is a leaf ($u.left = \text{NIL} \land u.right = \text{NIL}$), return TRUE.
- _Recursive Case:_ If one child is $\text{NIL}$ and the other is not, return FALSE. If both children exist, return $\text{IsFull}(u.left) \land \text{IsFull}(u.right)$.
  **2. Pseudocode:**

```text
Algorithm IsFull(u):
    if u = NIL then return TRUE
    if u.left = NIL u.right = NIL then return TRUE
    if u.left = NIL u.right = NIL then return FALSE
    return IsFull(u.left) IsFull(u.right)
```

**3. Complexity:**

- Worst Case: $\Theta(n)$, when the tree is full or the violation is at the very last visited node.
- Best Case: $O(1)$, when the root has exactly one child.
- Space: $O(h)$ stack space.
  **4. Perfectly Balanced Extension:**
  Return the depth of the subtree if it is full and perfectly balanced, or $-1$ otherwise. A leaf returns depth 0. An internal node checks whether both subtrees are non-negative and have equal depth $d$; if so, it returns $d + 1$, else $-1$.
