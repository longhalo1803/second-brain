---
title: "What is the computational cost in the worst case for hash tables with separate cha..."
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
  - "What is the computational cost in the worst case for hash tables with separate cha..."
---

# 🎴 What is the computational cost in the worst case for hash tables with separate cha...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: What is the computational cost in the **worst case** for hash tables with separate chaining? #card

?
In the **worst case**, the hash function maps **all $n$ stored keys to the exact same cell** $H[i]$.

In this unfavorable event, the table degrades into a single linked list of length $n$:

- `insert`: **$O(1)$** (always inserting at the head of the list).
- `lookup`: **$O(n)$** (requires scanning the entire list of $n$ elements if the element is at the end or absent).
- `remove`: **$O(n)$** (time required to locate the node in the list before deleting it).Assuming that computing $h(k)$ takes $\Theta(1)$.
