---
title: "What are the fundamental primitives of the Linked List data structure"
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
  - "What are the fundamental primitives of the Linked List data structure"
---

# 🎴 What are the fundamental primitives of the Linked List data structure

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: What are the fundamental primitives of the Linked List data structure? #card

?
The 7 fundamental primitives of the list are:

- `new_list()`: creates and returns a new empty list.
- `is_empty_list(L)`: checks if list `L` is empty.
- `insert_head(L, e)`: inserts node `e` at the head of list `L`.
- `insert_next(p, e)`: inserts node `e` immediately after node `p`.
- `search(L, i)`: searches and returns the pointer to the node at position `i`.
- `insert_pos(L, e, i)`: inserts node `e` at position `i`.
- `delete(L, p)`: removes from list `L` the node pointed to by `p`.⚠️ Warning: some are procedures (they do not return any value) while others are functions with a return value.
