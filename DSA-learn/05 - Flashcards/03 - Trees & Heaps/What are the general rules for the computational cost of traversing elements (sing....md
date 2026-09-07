---
title: "What are the general rules for the computational cost of traversing elements (sing..."
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
  - "What are the general rules for the computational cost of traversing elements (sing..."
---

# 🎴 What are the general rules for the computational cost of traversing elements (sing...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What are the general rules for the computational cost of **traversing **elements (single items, pairs, triplets, subsets, permutations), assuming that traversal and operations on elements individually have constant cost? #card

?
Cost of traversing:

- Sequence of $n$ elements: $O(n)$.
- All pairs: $O(n^2)$.
- All triplets: $O(n^3)$.
- All subsets: $O(2^n)$.
- All permutations: $O(n!)$.
