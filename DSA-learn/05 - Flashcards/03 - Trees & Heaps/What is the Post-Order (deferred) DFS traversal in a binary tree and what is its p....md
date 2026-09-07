---
title: "What is the Post-Order (deferred) DFS traversal in a binary tree and what is its p..."
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
  - "What is the Post-Order (deferred) DFS traversal in a binary tree and what is its p..."
---

# 🎴 What is the Post-Order (deferred) DFS traversal in a binary tree and what is its p...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 🟢 What is the **Post-Order** (deferred) DFS traversal in a binary tree and what is its pseudocode?

📝 What traversal order would result from this tree? Write the sequence: #card
?
In **Post-Order** (deferred) traversal, for each node we first process the **LEFT** subtree, then the **RIGHT** subtree, and finally the **ROOT**.

```text
DFS_post_order(t)
    if NOT (t = NIL) then
        DFS_post_order(t.left)
        DFS_post_order(t.right)
                {#fa1105}{{print} t.val} {#fa1105}{// process t}
```

Main call: $\textsf{DFS_post_order(T)}$

📌 Typical application: post-order traversal is used for bottom-up operations such as deleting/deallocating a tree or evaluating syntax expressions.

📝 Example:

Prints the following sequence:

H,I,D,L,E,B,F,M,G,C,A

Recursive calls:

((((()()H)(()()I)D)(()(()()L)E)B)((()()F)((()()M)()G)C)A)
