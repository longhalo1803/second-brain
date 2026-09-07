---
title: "📘 Exercise 2.1"
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
  - "📘 Exercise 2.1"
---

# 🎴 📘 Exercise 2.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 2.1

**Input:** A binary tree implemented with nodes and pointers (fields $left, right, key$) storing integer values.
**Output:** The number of leaves whose key is twice the key of their parent.

- Show an example of input and output with a tree having at least 8 leaves.
- Describe a recursive algorithm indicating the base case, recursive case, and actions taken.
- Write the pseudocode of the algorithm.
- Analyze the computational complexity.
- Assuming nodes have identifiers $\{1, \dots, n\}$ and the tree is represented by a parent array $P[1 \dots n]$ where $P[i] = (p, key)$ ($p$ is parent ID, $key$ is node key), describe how to solve the problem without requiring recursion. #card
  ?
  **Reasoning:**
  During a recursive traversal, pass the parent key to child calls. If a visited node is a leaf, check whether $leaf.key = 2 \cdot parent.key$. For the parent array representation, a node is a leaf if its index does not appear as a parent pointer of any node.

**1. Example:**
Consider a full binary tree with 8 leaves. If parents have keys $10, 20, 30, 40$ and 3 of the leaves have values $20, 40, 80$ matching twice their respective parents, the output is $3$.

**2. Recursive Strategy:**

- _Base Case:_ If $u = \text{NIL}$, return 0. If $u$ is a leaf, return 1 if $u.key = 2 \cdot parent\_key$, else 0.
- _Recursive Case:_ If $u$ is an internal node, recursively compute the count in $u.left$ and $u.right$ passing $u.key$ as parent key, returning the sum.
  **3. Pseudocode:**

```text
Algorithm CountDoubleLeaves(T):
    if T = NIL then return 0
    return CountRec(T.left, T.key) + CountRec(T.right, T.key)

Function CountRec(u, parent_key):
    if u = NIL then return 0
    if u.left = NIL u.right = NIL then
        return (u.key = 2 parent_key \,?\, 1 : 0)
    return CountRec(u.left, u.key) + CountRec(u.right, u.key)
```

**4. Complexity:**

- Time Complexity: $\Theta(n)$, where $n$ is the number of nodes, as every node is visited once.
- Space Complexity: $O(h)$ auxiliary stack space, where $h$ is tree height.
  **5. Parent Array Variant:**
  Allocate a boolean array $is\_parent[1 \dots n]$ initialized to false. In a first pass over $i \in \{1 \dots n\}$, if $P[i].p \ne 0$, set $is\_parent[P[i].p] \leftarrow \text{true}$. In a second pass, for each $i$, if $is\_parent[i] = \text{false}$ and $P[i].p \ne 0$ and $P[i].key = 2 \cdot P[P[i].p].key$, increment a counter. Time complexity is $\Theta(n)$ and auxiliary space is $\Theta(n)$.
