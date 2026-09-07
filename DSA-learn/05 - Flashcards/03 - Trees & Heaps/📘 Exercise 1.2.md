---
title: "📘 Exercise 1.2"
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
  - "📘 Exercise 1.2"
---

# 🎴 📘 Exercise 1.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 1.2

**Input:** A binary tree $T$ implemented with nodes and pointers (fields $left, right, val$) storing integer values.
**Output:** Modify the tree by copying the key stored in the root of $T$ into all leaves.

- Show an example of input and output on a tree with 10 nodes.
- Describe a recursive algorithm, specifying base and recursive cases.
- Write the pseudocode of the algorithm.
- Show the order of recursive calls and their termination on the provided example.
- Analyze the computational complexity. #card
  ?
  **Reasoning:**
  We can read the root value once and propagate it down recursively. Whenever a leaf is reached (a node where both children are $\text{NIL}$), its value is overwritten with the root value.

**1. Example:**
Let $T$ have root key $50$ and 10 nodes, with leaves containing keys $[3, 7, 12, 19]$. After execution, all internal nodes retain their original values, while each leaf's value is set to $50$.

**2. Algorithm Description:**

- _Base Case:_ If the node is $\text{NIL}$, return. If the node is a leaf ($u.left = \text{NIL} \land u.right = \text{NIL}$), set $u.val \leftarrow root\_val$ and return.
- _Recursive Case:_ If $u$ is an internal node, recursively call the function on $u.left$ and $u.right$, passing $root\_val$.
  **3. Pseudocode:**

```text
Algorithm CopyRootToLeaves(T):
    if T ≠ NIL then
        UpdateLeaves(T, T.val)

Procedure UpdateLeaves(u, root_val):
    if u = NIL then return
    if u.left = NIL u.right = NIL then
        u.val ≤ftarrow root_val
        return
    UpdateLeaves(u.left, root_val)
    UpdateLeaves(u.right, root_val)
```

**4. Call Order and Termination:**
Starting from the root, the traversal explores the left subtree recursively down to the leftmost leaf, updates it, terminates the frame, backtracks to visit right siblings, and proceeds in pre-order across all nodes until all calls terminate.

**5. Complexity:**

- Time Complexity: $\Theta(n)$, as each of the $n$ nodes is visited once.
- Space Complexity: $O(h)$ auxiliary stack frames, where $h$ is tree height ($O(\log n)$ best case, $O(n)$ worst case).
