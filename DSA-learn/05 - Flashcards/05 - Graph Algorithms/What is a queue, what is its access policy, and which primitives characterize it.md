---
title: "What is a queue, what is its access policy, and which primitives characterize it"
tags:
  - dsa
  - flashcards
  - clrs
  - graphs
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "What is a queue, what is its access policy, and which primitives characterize it"
---

# 🎴 What is a queue, what is its access policy, and which primitives characterize it

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: What is a queue, what is its access policy, and which primitives characterize it? #card

?
A queue is a **sequential data structure** in which:

- The stored values are all of the same type.
- New values are inserted at the back (_tail_) of the queue (**ENQUEUE** operation).
- Extraction removes the value at the front (_head_) of the queue (**DEQUEUE** operation).
  **Access policy:** **FIFO** (_First In, First Out_ — the first one in is the first one out).

**Queue primitives:**

- `new_queue()`: creates a new empty queue.
- `is_empty_queue(Q)`: checks whether queue `Q` is empty.
- `enqueue(Q, x)`: inserts element `x` at the back (tail) of the queue.
- `first(Q)`: returns the value at the front (head) of the queue without removing it.
- `dequeue(Q)`: removes and returns the value at the front of the queue.
