---
title: "What are the fundamental operations of a Min-Priority Queue"
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
  - "What are the fundamental operations of a Min-Priority Queue"
---

# 🎴 What are the fundamental operations of a Min-Priority Queue

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What are the fundamental operations of a Min-Priority Queue? #card

?
Assuming that highest priority corresponds to the minimum `pr` value:

- `Make_priority_queue(Q')`: creates and returns a new priority queue containing the pairs of the set `Q'`.
- `is_empty_queue(Q)`: returns `TRUE` if the queue is empty, `FALSE` otherwise.
- `EnQueue(Q, el, pr)`: inserts a new pair `(el, pr)` into the queue.
- `MinQueue(Q)`: returns the element `el` with the highest priority (minimum `pr` value) without removing it.
- `DeQueue(Q)`: removes the pair with the highest priority (minimum `pr` value) and returns its element `el`.
- `Decrease_Priority(Q, el, pr)`: modifies the pair `(el, pr')` in the queue by updating the priority of element `el`, setting a value `pr < pr'`.
