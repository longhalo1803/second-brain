---
title: "What is the Pre-Order DFS traversal in a binary tree and what is its pseudocode"
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
  - "What is the Pre-Order DFS traversal in a binary tree and what is its pseudocode"
---

# 🎴 What is the Pre-Order DFS traversal in a binary tree and what is its pseudocode

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 🟢 What is the **Pre-Order** DFS traversal in a binary tree and what is its pseudocode?

📝 What traversal order would result from this tree? Write the sequence: #card
?
In **Pre-Order** traversal, for each node we first process the **ROOT**, then the **LEFT** subtree, and finally the **RIGHT** subtree.

```text
DFS_pre_order(t)
    if NOT (t = NIL) then
                {#fa1105}{{print} t.val} {#fa1105}{// process t}
        DFS_pre_order(t.left)
        DFS_pre_order(t.right)
```

Main call: $\textsf{DFS_pre_order(T)}$

📝 Example:

Prints the following sequence:

A,B,D,H,I,E,L,C,F,G,M

Recursive calls:

(A(B(D(H()())(I()()))(E()(L()())))(C(F()())(G(M()())())))
