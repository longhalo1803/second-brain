---
title: "How is the representation of a queue structured using a linked list Draw it."
tags:
  - dsa
  - flashcards
  - clrs
  - data-structures
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "How is the representation of a queue structured using a linked list Draw it."
---

# 🎴 How is the representation of a queue structured using a linked list Draw it.

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: How is the representation of a queue structured using a linked list? Draw it. #card

?
To guarantee a cost of $\Theta(1)$ for both insertion and extraction, the queue `Q` is represented by a **pointer** to a node containing **two pointers**:

- **`head`:** points to the first node of the list (the oldest element, where `dequeue` occurs).
- **`tail`:** points to the last node of the list (the newest element, where `enqueue` occurs).
