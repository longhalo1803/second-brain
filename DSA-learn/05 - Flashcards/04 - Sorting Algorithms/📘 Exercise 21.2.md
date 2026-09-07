---
title: "📘 Exercise 21.2"
tags:
  - dsa
  - flashcards
  - clrs
  - sorting
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "📘 Exercise 21.2"
---

# 🎴 📘 Exercise 21.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📘 Exercise 21.2

**Input:** A sorted array $A$ of $n$ natural numbers, where $n = 2^m - 1$ for some integer $m \ge 1$.
**Output:** Construct a perfectly balanced Binary Search Tree (BST) whose keys are the values in $A$.

- Show an example with $m \ge 3$ of input and output.
- Describe an algorithm in words, motivating the design.
- Provide pseudocode.
- Analyze computational complexity. #card
  ?
  **Reasoning:**
  To create a perfectly balanced BST from a sorted array, the middle element must be the root, its left subarray forms the left balanced subtree, and its right subarray forms the right balanced subtree.

**1. Example:**
Let $m = 3 \implies n = 2^3 - 1 = 7$. $A = [10, 20, 30, 40, 50, 60, 70]$.
Middle is $40$ (root). Left child is $20$ (with leaves $10, 30$); right child is $60$ (with leaves $50, 70$). Perfectly balanced BST of height 2.

**2. Algorithm Description:**
Recursively pick $mid = \lfloor (low + high) / 2 \rfloor$ as the root node. Recursively construct the left child from $[low, mid - 1]$ and the right child from $[mid + 1, high]$. Base case: when $low > high$, return NIL.

**3. Pseudocode:**

```text
Function BuildBalancedBST(A, low, high):
    if low > high then return NIL
    mid ≤ftarrow floor( (low + high) / 2 )
    node ≤ftarrow new TreeNode(A[mid])
    node.left ≤ftarrow BuildBalancedBST(A, low, mid - 1)
    node.right ≤ftarrow BuildBalancedBST(A, mid + 1, high)
    return node

Algorithm CreateBalancedBST(A, n):
    return BuildBalancedBST(A, 0, n - 1)
```

**4. Complexity:**
Recurrence: $T(n) = 2T(n/2) + O(1) \implies \Theta(n)$ time. Space complexity: $O(\log n)$ stack space.
