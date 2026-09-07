---
title: "10 Given two binary trees T1 and T2, write a recursive function SameStructure(T1,..."
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
  - "10 Given two binary trees T1 and T2, write a recursive function SameStructure(T1,..."
---

# 🎴 10 Given two binary trees T1 and T2, write a recursive function SameStructure(T1,...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📝 10 Given two binary trees $T_1$ and $T_2$, write a recursive function `SameStructure(T1, T2)` that returns `TRUE` if the two trees have the same structure, and `FALSE` otherwise. Analyze its computational cost.

Examples of binary trees with the same structure (top) and different structure (bottom). Note that a
right child is different from a left child. #card
?
**Base case:**
• Both trees empty (`T1 = NIL` and `T2 = NIL`): returns `TRUE`.
• Only one of the two trees empty (`T1 = NIL` or `T2 = NIL`): returns `FALSE`.
**Recursive case:**
Both trees non-empty: recursively compares the left subtrees and the right subtrees. Returns `TRUE` if both checks succeed.

**Pseudocode:**

```text
SameStructure(T1, T2)
    if T1 = NIL AND T2 = NIL then return TRUE
    if T1 = NIL OR T2 = NIL then return FALSE
    return (SameStructure(T1.left, T2.left) AND SameStructure(T1.right, T2.right))
```

📌 Note: logically the second `if` should use an XOR, but thanks to the execution order of the instructions (_short-circuit evaluation_) the behavior is equivalent to OR:
we only reach the second `if` if the first condition was false (meaning they are not both `NIL`); consequently, if `T1 = NIL OR T2 = NIL` evaluates to true there, it necessarily means that only one of the two is NIL (it evaluates to false only if neither is null). The case in which both statements are null was already "discarded" by the first `if` + `return`.

**Computational cost:**
In the worst case (which occurs when both trees have the same structure), the algorithm visits all nodes performing constant work on each:
Cost: $\Theta(n)$ (or $\Theta(n + m)$ for trees of sizes $n$ and $m$).
