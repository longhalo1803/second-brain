---
title: "📘 Exercise 4.2"
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
  - "📘 Exercise 4.2"
---

# 🎴 📘 Exercise 4.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 4.2

Given a binary tree $T = (V, E)$ and a node $v \in V$, let $\text{imbalance}(v) = |\text{leaves}(left(v)) - \text{leaves}(right(v))|$, with $\text{imbalance}(v) = 0$ if $v$ is a leaf. The tree imbalance is $\text{imbalance}(T) = \max_{v \in V} \text{imbalance}(v)$.

**Input:** A full binary tree $T$ (where every node has 0 or 2 children) implemented with nodes and pointers.
**Output:** $\text{imbalance}(T)$.

- Show an example with at least 8 nodes.
- Explain an algorithm to solve the problem.
- Provide the pseudocode.
- Analyze the computational complexity.
- Show an instance where $\text{imbalance}(T) = \text{imbalance}(v)$ and $v$ is not the root.
- For a full binary tree with $f$ leaves, what is the maximum possible value of $\text{imbalance}(T)$? Explain and give an example. #card
  ?
  **Reasoning:**
  A post-order traversal computes the number of leaves in the left and right subtrees for each node, determines the local imbalance, and tracks the maximum imbalance across the entire tree in a bottom-up manner.

**1. Example:**
Consider a full binary tree where root's left child is a leaf (1 leaf), and root's right child is the root of a full subtree with 4 leaves. Total nodes = 9 ($\ge 8$). Imbalance at root is $|1 - 4| = 3$. Output: 3.

**2. Algorithm Description:**
Perform a post-order traversal returning a pair $(leaves, max\_imb)$. For a leaf, return $(1, 0)$. For an internal node, recursively obtain $(l_L, m_L)$ and $(l_R, m_R)$. The number of leaves is $l_L + l_R$, local imbalance is $|l_L - l_R|$, and maximum imbalance is $\max(|l_L - l_R|, m_L, m_R)$.

**3. Pseudocode:**

```text
Function ComputeImbalance(u):
    if u.left = NIL u.right = NIL then return (1, 0)
    (l_L, m_L) ≤ftarrow ComputeImbalance(u.left)
    (l_R, m_R) ≤ftarrow ComputeImbalance(u.right)
    local_imb ≤ftarrow |l_L - l_R|
    max_imb ≤ftarrow (local_imb, m_L, m_R)
    return (l_L + l_R, max_imb)

Algorithm TreeImbalance(T):
    if T = NIL then return 0
    (leaves, max_imb) ≤ftarrow ComputeImbalance(T)
    return max_imb
```

**4. Complexity:**

- Time Complexity: $\Theta(n)$, visiting each node once.
- Space Complexity: $O(h)$ auxiliary recursion stack space.
  **5. Non-root Max Instance:**
  Let the root have left and right subtrees each with 10 leaves ($\text{imbalance}(root) = 0$). In the left subtree, let its root have one child with 1 leaf and the other with 9 leaves ($\text{imbalance} = 8$). Here $\text{imbalance}(T) = 8$ attained at a non-root node.

**6. Maximum Imbalance with $f$ Leaves:**
The maximum imbalance is $f - 2$. A node with $k$ leaves achieves maximum imbalance when one child is a single leaf and the other has $k - 1$ leaves, giving $|(k - 1) - 1| = k - 2$. For the entire tree, this is maximized at $k = f$, yielding $f - 2$.
