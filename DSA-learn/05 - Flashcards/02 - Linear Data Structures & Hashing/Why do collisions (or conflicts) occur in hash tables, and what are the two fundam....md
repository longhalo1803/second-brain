---
title: "Why do collisions (or conflicts) occur in hash tables, and what are the two fundam..."
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
  - "Why do collisions (or conflicts) occur in hash tables, and what are the two fundam..."
---

# 🎴 Why do collisions (or conflicts) occur in hash tables, and what are the two fundam...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: Why do **collisions (or conflicts)** occur in hash tables, and what are the two fundamental approaches to handle them? #card

?
Given a universe of keys $U$ and a table of size $m$, if the potential number of keys is greater than the number of slots ($|U| > m$), by the _pigeonhole principle_:

$$

\exists \, k_1, k_2 \in U \text{ with } k_1 \neq k_2 \text{ such that } h(k_1) = h(k_2)

$$

A **collision** therefore occurs: two different keys attempt to occupy the same cell $H[h(k)]$.

To handle conflicts, one must provide alternative positions and keep computational costs low. The two main techniques are:

- **Separate Chaining**: each slot of the array points to a linked list of conflicting elements.
- **Open Addressing**: all elements reside directly in the slots of the array; if a slot is occupied, an alternative sequence of indices is probed.
