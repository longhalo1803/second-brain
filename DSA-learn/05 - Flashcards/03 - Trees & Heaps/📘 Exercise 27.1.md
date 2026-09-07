---
title: "📘 Exercise 27.1"
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
  - "📘 Exercise 27.1"
---

# 🎴 📘 Exercise 27.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 27.1

**Input:** A binary tree $T$ storing distinct positive integers, and a positive integer $k$ stored in $T$.
**Output:** Print the keys of all ancestors of the node storing $k$ (from root down to parent), followed by "fine".

- Show an example with height at least 3 where $k$ is not in the root.
- Describe a recursive algorithm specifying base and recursive cases.
- Provide pseudocode.
- Analyze computational complexity. #card
  ?
  **Reasoning:**
  A recursive traversal returns true if node $k$ is found in the subtree. When a child call returns true, the current node is an ancestor. Printing before the recursive call outputs ancestors from root down to parent.

**1. Example:**
Root $10 \to$ left child $5 \to$ right child $7 \to$ left child $k = 3$. Ancestors are $10, 5, 7$. Output: $10, 5, 7$, fine.

**2. Algorithm Description:**
Define a recursive function `FindAncestors(u, k)`. If $u = \text{NIL}$, return false. If $u.val = k$, return true. Otherwise, check left subtree; if true, print $u.val$ and return true. If false, check right subtree; if true, print $u.val$ and return true. In the main procedure, call `FindAncestors(T, k)` and then print "fine".

**3. Pseudocode:**

```text
Function PrintPathToK(u, k):
    if u = NIL then return FALSE
    if u.val = k then return TRUE
    if PrintPathToK(u.left, k) PrintPathToK(u.right, k) then
        output_list.append(u.val)
        return TRUE
    return FALSE

Algorithm PrintAncestorsOfK(T, k):
    output_list ≤ftarrow new empty list
    PrintPathToK(T, k)
    for each val ∈ reverse(output_list) do print val
    print "fine"
```

**4. Complexity:**
$O(n)$ time, visiting each node at most once, and $O(h)$ auxiliary stack space.
