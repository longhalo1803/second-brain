---
title: "How are Pre-Order and Post-Order DFS traversals adapted for general trees"
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
  - "How are Pre-Order and Post-Order DFS traversals adapted for general trees"
---

# 🎴 How are Pre-Order and Post-Order DFS traversals adapted for general trees

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: How are Pre-Order and Post-Order DFS traversals adapted for general trees? #card

?
In **general trees**, each node can have an arbitrary number of children given by `children(t)`.

**Pre-Order DFS for general trees:**

```text
DFS_pre_order(t)
    if NOT (t = NIL) then
                {#fa1105}{{print} t.val} {#fa1105}{// process t}
        for all u ∈ children(t) do
            DFS_pre_order(u)
```

Main call: $\textsf{DFS_pre_order(T)}$

📝 Example:

Prints the following sequence:

A,B,F,C,G,D,H,L,M,N,I,E

Recursive calls:

(A(B()(F()()))(C()(G()()))(D(H(L()())(M()())(N()()))(I()()))(E()()))

**Post-Order DFS for general trees:**

```text
DFS_post_order(t)
    if NOT (t = NIL) then
        for all u ∈ children(t) do
            DFS_post_order(u)
                {#fa1105}{{print} t.val} {#fa1105}{// process t}
```

Main call: $\textsf{DFS_post_order(T)}$

📝 Example:

Prints the following sequence:

F,B,G,C,L,M,N,H,I,D,E,A

Recursive calls:

(((()(F()())B)((()(G()())C)(((()()L)(()()M)(()()N)H)(()()I)D)(()()E)A)

📌 Note: for general trees, _In-Order_ traversal is not defined because there is no single reference left/right subtree.
