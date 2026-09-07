---
title: "What are the fundamental primitives of the Dictionary ADT"
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
  - "What are the fundamental primitives of the Dictionary ADT"
---

# 🎴 What are the fundamental primitives of the Dictionary ADT

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: What are the **fundamental primitives** of the Dictionary ADT? #card

?
The primitive operations are:

- `new_dictionary()`: instantiates and returns an empty dictionary.
- `lookup(D, k)`: searches for and returns the value $v$ associated with key $k$ in dictionary $D$ if present, otherwise returns `NIL`.
- `insert(D, k, v)`: associates value $v$ with key $k$ in dictionary $D$; if key $k$ was already present, the preexisting association is overwritten with the new value.
- `remove(D, k)`: deletes the pair associated with key $k$ from dictionary $D$.
