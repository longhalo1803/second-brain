---
title: "📘 Exercise 31.1"
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
  - "📘 Exercise 31.1"
---

# 🎴 📘 Exercise 31.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 31.1

**Input:** A binary tree $T$ implemented with nodes and pointers (fields $val, left, right$) storing integer values.
**Output:** For every root-to-leaf path, considering leaves from left to right, print the sum of all values stored in the nodes of that path (root and leaf included).

- Show an example of input and output with a tree of height at least 2.
- Describe a recursive algorithm, specifying base and recursive cases.
- Provide the pseudocode.
- Analyze the computational complexity. #card
  ?
  **Reasoning:**
  Traversing the tree using depth-first search (DFS) visiting the left child before the right child naturally visits leaves in left-to-right order. By passing the accumulated path sum down the recursion stack, the path sum is immediately available when a leaf is encountered.

**1. Example:**
Tree of height 2: Root $A(5)$. Left child $B(3)$, with leaves $D(1)$ and $E(4)$. Right child $C(8)$, with leaf $F(2)$.
Paths (left to right):

- Path $A \to B \to D$: sum $= 5 + 3 + 1 = 9$
- Path $A \to B \to E$: sum $= 5 + 3 + 4 = 12$
- Path $A \to C \to F$: sum $= 5 + 8 + 2 = 15$Output: 9, 12, 15.

**2. Recursive Strategy:**

- _Base Case:_ If current node $u = \text{NIL}$, return. If $u$ is a leaf ($u.left = \text{NIL} \land u.right = \text{NIL}$), print $current\_sum + u.val$ and return.
- _Recursive Case:_ If $u$ is an internal node, recursively visit $u.left$ with sum $current\_sum + u.val$, then recursively visit $u.right$ with sum $current\_sum + u.val$.
  **3. Pseudocode:**

```text
Procedure PrintPathSumsRec(u, current_sum):
    if u = NIL then return
    new_sum ≤ftarrow current_sum + u.val
    if u.left = NIL u.right = NIL then
        print new_sum
        return
    PrintPathSumsRec(u.left, new_sum)
    PrintPathSumsRec(u.right, new_sum)

Algorithm PrintRootToLeafSums(T):
    PrintPathSumsRec(T, 0)
```

**4. Complexity:**

- Time Complexity: $\Theta(n)$, where $n$ is the number of nodes in $T$, since every node is visited exactly once.
- Space Complexity: $O(h)$ auxiliary recursion stack space, where $h$ is the tree height ($O(\log n)$ best case, $O(n)$ worst case).
