---
title: "Write the pseudocode for BFS (Breadth-First Search) traversal for general trees us..."
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
  - "Write the pseudocode for BFS (Breadth-First Search) traversal for general trees us..."
---

# 🎴 Write the pseudocode for BFS (Breadth-First Search) traversal for general trees us...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📝🟢 Write the pseudocode for BFS (Breadth-First Search) traversal for general trees **using the FirstChild-NextSibling representation**. #card

?
A node $u$ is dequeued from the queue, its value is processed, and then all its children are enqueued into the queue by traversing the chain of siblings starting from `u.firstchild` onward via `nextsibling`.

**Pseudocode:**

```text
BFS(T)
    if NOT (T = NIL) then
        Q := new_queue()
        enqueue(Q, T)
        while NOT is_empty_queue(Q) do
            u := dequeue(Q)
                    {#fa1105}print u.val {#fa1105}{// process u}
            w := u.firstchild
            while NOT (w = NIL) do
                enqueue(Q, w)
                w := w.nextsibling
```
