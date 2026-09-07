---
title: "5 Given a binary tree T, write a recursive algorithm to modify T so as to store in..."
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
  - "5 Given a binary tree T, write a recursive algorithm to modify T so as to store in..."
---

# 🎴 5 Given a binary tree T, write a recursive algorithm to modify T so as to store in...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📝 5 Given a binary tree $T$, write a **recursive** algorithm to modify T so as to store in the `val` (or `key`) field of each node $v$ the number of nodes in the subtree rooted at $v$ (root included).

Compare the cost of the single-traversal solution with the alternative that recalculates nodes for each level. #card
?
**Optimized solution (Bottom-Up, **$\Theta(n)$**)\****:**
We compute the subtree size on the return path of the recursion and store the value directly into the current node.

```text
ModifyTree(T)
    if T ≠q NIL then c := CountNodes(T)
```

```text
CountNodes(t)
    c := 0
    if t ≠q NIL then
        c := CountNodes(t.left) + CountNodes(t.right) + 1
        t.key := c
    return c
```

**Alternative solution (Inefficient):**
Performs a traversal of the tree and separately calls the counting function for each node:

```text
ModifyTree(t)
    if t ≠q NIL then
        t.val := CountNodes(t)
        ModifyTree(t.left)
        ModifyTree(t.right)
```

```text
CountNodes(t)
    if t ≠q NIL then
        return CountNodes(t.left) + CountNodes(t.right) + 1
```

**📌 Comparison of Computational Costs:**

- **First solution (Optimized):** Performs a tree traversal and, for each node, executes a constant number of operations, so the computational cost is dominated by the number of nodes to visit and is $\Theta(n)$. It is $\Theta$ because all nodes must be visited; none can be skipped in any case (even in the best case).
- **Second solution (Inefficient):** For each node $\textsf{v}$ encountered during the traversal of $\textsf{ModifyTree}$, it makes a call to $\textsf{CountNodes}$ and this, unlike before, does not have constant cost, but depends on the number of nodes in the subtree rooted at $\textsf{v}$. To determine the computational cost it is therefore necessary to evaluate the sum of the costs of all calls to $\textsf{CountNodes}$.
  The worst case we can imagine is that, for each node, the call to $\textsf{CountNodes}$ costs $O(n)$ (no more is possible because the tree has at most $n$ nodes), so we can state that the solution has a cost of $O(n^2)$. If we can find at least one case in $\Omega(n^2)$ (i.e., the cost actually depends on $n^2$ and not on a lower-order function), then we can conclude that this version has computational cost $\Theta(n^2)$ and is therefore, in the worst case, less efficient than the first.
- ❓ Is there a tree where a non-constant number of nodes of $\textsf{T}$ (for example $n/2$, assuming $n$ even for simplicity) has at least one subtree containing a non-constant number of nodes (for example at least $n/2$)?
- One case is that of a degenerate tree where each node has only one child: the nodes of the first $n/2$ levels have at least $n/2$ nodes in their subtrees. This simple example is sufficient for our purpose (we can never find a case with order of magnitude greater than $n^2$, having an upper bound of $O(n^2)$).
