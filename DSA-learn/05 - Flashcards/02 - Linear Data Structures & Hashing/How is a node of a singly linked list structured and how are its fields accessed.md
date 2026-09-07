---
title: "How is a node of a singly linked list structured and how are its fields accessed"
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
  - "How is a node of a singly linked list structured and how are its fields accessed"
---

# 🎴 How is a node of a singly linked list structured and how are its fields accessed

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: How is a node of a singly linked list structured and how are its fields accessed? #card

?
A node of a singly linked list consists of two main fields:

**`• val`:** contains the stored **data** (e.g. sequence value).
**`• next`:** contains the **reference (pointer) to the next node** in the list (or `NIL`/`NULL` if it is the last node).

Given a pointer **`e`** to a node:

**`• e.val`** allows accessing/modifying the data.
**`• e.next`** allows accessing/modifying the pointer to the next node.
