---
title: "What is the In-Order (symmetric) DFS traversal in a binary tree and what is its ps..."
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
  - "What is the In-Order (symmetric) DFS traversal in a binary tree and what is its ps..."
---

# 🎴 What is the In-Order (symmetric) DFS traversal in a binary tree and what is its ps...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 🟢 What is the **In-Order** (symmetric) DFS traversal in a binary tree and what is its pseudocode?

📝 What traversal order would result from this tree? Write the sequence: #card
?
In **In-Order** (symmetric) traversal, for each node we first process the **LEFT** subtree, then the **ROOT**, and finally the **RIGHT** subtree.

```text
DFS_in_order(t)
    if NOT (t = NIL) then
        DFS_in_order(t.left)
                {#fa1105}{{print} t.val} {#fa1105}{// process t}
        DFS_in_order(t.right)
```

Main call: $\textsf{DFS_in_order(T)}$

📌 Note: in Binary Search Trees (BST), In-Order traversal visits the keys in perfectly ascending order.

📝 Example:

Prints the following sequence:

H,D,I,B,E,L,A,F,C,M,G

Recursive calls:

((((()H())D(()I()))B(()E(()L())))A((()F())C((()M())G())))
