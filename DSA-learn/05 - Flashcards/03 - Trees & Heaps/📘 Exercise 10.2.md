---
title: "📘 Exercise 10.2"
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
  - "📘 Exercise 10.2"
---

# 🎴 📘 Exercise 10.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 10.2

The _left view_ of a binary tree is the list of nodes visible when the tree is viewed from the left side, ordered by increasing depth (one node per level).

**Input:** A binary tree $T$ implemented with nodes and pointers (fields $key, left, right$).
**Output:** Print the keys of the nodes comprising the left view of $T$.

Describe an algorithm in words, provide pseudocode, and analyze its computational complexity. #card
?
**Reasoning:**
The left view consists of the first node encountered at each depth level. We can perform a preorder traversal (root, left, right), passing the current depth. By tracking the maximum depth printed so far, we print the key whenever the current depth exceeds the recorded maximum depth.

**Algorithm Description:**
Maintain an integer $max\_depth$ initialized to $-1$. A recursive helper takes node $u$ and current $depth$ (starting at 0 for root). If $u = \text{NIL}$, return. If $depth > max\_depth$, print $u.key$ and update $max\_depth \leftarrow depth$. Then recursively visit $u.left$ followed by $u.right$ at $depth + 1$.

**Pseudocode:**

```text
Algorithm LeftView(T):
    max_depth ≤ftarrow -1
    LeftViewRec(T, 0, max_depth)

Procedure LeftViewRec(u, depth, ref max_depth):
    if u = NIL then return
    if depth > max_depth then
        print u.key
        max_depth ≤ftarrow depth
    LeftViewRec(u.left, depth + 1, max_depth)
    LeftViewRec(u.right, depth + 1, max_depth)
```

**Complexity:**

- Time Complexity: $\Theta(n)$, where $n$ is the number of nodes, as each node is visited once.
- Space Complexity: $O(h)$ recursion stack frames, where $h$ is tree height.
