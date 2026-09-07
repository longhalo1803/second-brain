---
title: "How does Breadth-First Search (BFS) work in a general tree Write the corresponding..."
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
  - "How does Breadth-First Search (BFS) work in a general tree Write the corresponding..."
---

# 🎴 How does Breadth-First Search (BFS) work in a general tree Write the corresponding...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 🟢 How does Breadth-First Search (BFS) work in a general tree? Write the corresponding pseudocode. #card

?
The **BFS (Breadth First Search) traversal** explores the tree level by level (from top to bottom and left to right). It uses a **queue** to maintain the traversal order of the nodes.

**Pseudocode:**

```text
BFS(T)
    if NOT (T = NIL) then
        Q := new_queue()
        enqueue(Q, T)
        while NOT is_empty_queue(Q) do
            u := dequeue(Q)
                    {#fa1105}{{print} u.val} {#fa1105}{// process u}
            for all v ∈ children(u) do
                enqueue(Q, v)
```

📝 Example:

Prints the following sequence:

A,B,C,D,E,F,G,H,I,L,M,N

**Queue evolution (BFS):
**

      Extracted Node
      Children Inserted into Q
      Queue Q State (Head → Tail)



    --**[ A ]**
    AB, C, D, E[ B, C, D, E ]
    BF[ C, D, E, F ]
    CG[ D, E, F, G ]
    DH, I[ E, F, G, H, I ]
    E—[ F, G, H, I ]
    F—[ G, H, I ]
    G—[ H, I ]
    HL, M, N[ I, L, M, N ]
    I—[ L, M, N ]
    L—[ M, N ]
    M—[ N ]
    N—[ ]
