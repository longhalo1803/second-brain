---
title: "What are the three abstract operations of the Disjoint Set and what is their seman..."
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
  - "What are the three abstract operations of the Disjoint Set and what is their seman..."
---

# 🎴 What are the three abstract operations of the Disjoint Set and what is their seman...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What are the three abstract operations of the Disjoint Set and what is their semantic meaning? #card

?
The three abstract operations that define the interface of a Disjoint Set are:

1. `Make-set(X)`: Initializes the data structure, returning a Disjoint Set in which each element forms a singleton disjoint subset, that is, $S_i = \{i\}, \quad \forall i = 1, \dots, |X|$.
2. `Find-set(DS, x)`: Returns the unique **representative** element of the set to which element $x$ belongs.
3. `Union(DS, x, y)`: Merges the disjoint sets to which elements $x$ and $y$ respectively belong.

📌 Note:
The *representative *is a canonical element of the set used to test membership or equivalence of two elements (two elements belong to the same set if and only if they have the same representative).
