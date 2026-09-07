---
title: "📘 Exercise 30.1"
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
  - "📘 Exercise 30.1"
---

# 🎴 📘 Exercise 30.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 30.1

**Input:** A binary tree $T$ (fields: $val, left, right$) storing integers.
**Output:** TRUE if, for every node in $T$, the sum of keys in its left subtree equals the sum of keys in its right subtree, FALSE otherwise (the sum of an empty subtree is 0).

- Show an example of height at least 2.
- Describe a recursive algorithm specifying base and recursive cases.
- Provide pseudocode.
- Analyze computational complexity. #card
  ?
  **Reasoning:**
  A post-order traversal computes the sum of elements in the left and right subtrees. A node is valid if both child subtrees are valid and $sum(left) = sum(right)$.

**1. Example:**
Root $A(10)$. Left subtree is leaf $B(5)$ (sum = 5). Right subtree is leaf $C(5)$ (sum = 5). Both leaves have left and right sums of 0. For root, $5 = 5$. Output: TRUE.

**2. Algorithm Description:**
Define a recursive helper that returns $(is\_valid, subtree\_sum)$. If node is NIL, return $(\text{true}, 0)$. Recursively process left and right subtrees. The current node is valid if both subtrees are valid and $sum_L = sum_R$. Return $(\text{valid}, u.val + sum_L + sum_R)$.

**3. Pseudocode:**

```text
Function CheckEqualSubtrees(u):
    if u = NIL then return (true, 0)
    (ok_L, sum_L) ≤ftarrow CheckEqualSubtrees(u.left)
    (ok_R, sum_R) ≤ftarrow CheckEqualSubtrees(u.right)
    is_valid ≤ftarrow ok_L ok_R (sum_L = sum_R)
    return (is_valid, u.val + sum_L + sum_R)

Algorithm IsTreeBalancedInSum(T):
    (valid, sum) ≤ftarrow CheckEqualSubtrees(T)
    return valid
```

**4. Complexity:**
$\Theta(n)$ time, visiting each node once, and $O(h)$ auxiliary stack space.
