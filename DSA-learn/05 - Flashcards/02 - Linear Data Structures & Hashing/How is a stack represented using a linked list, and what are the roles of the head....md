---
title: "How is a stack represented using a linked list, and what are the roles of the head..."
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
  - "How is a stack represented using a linked list, and what are the roles of the head..."
---

# 🎴 How is a stack represented using a linked list, and what are the roles of the head...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: How is a stack represented using a linked list, and what are the roles of the head and the tail of the list? #card

?
In the implementation of a stack `S` via a linked list:

- `S` is the **pointer to the first node of the list**.
- **Head of the list:** stores the top of the stack (the most recently inserted value).
- **Tail of the list:** stores the bottom of the stack (the value inserted furthest back in time).

📌 Note: thanks to this choice, all insertion and removal operations (`push`, `pop`, `top`) occur at the head with a cost of $\Theta(1)$.
