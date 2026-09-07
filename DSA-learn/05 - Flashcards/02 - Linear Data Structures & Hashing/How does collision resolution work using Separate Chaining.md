---
title: "How does collision resolution work using Separate Chaining"
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
  - "How does collision resolution work using Separate Chaining"
---

# 🎴 How does collision resolution work using Separate Chaining

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: How does collision resolution work using **Separate Chaining**? #card

?
In the **chaining** approach, the array $H[0 \dots m-1]$ does not store data directly; instead, each cell $H[i]$ contains a pointer to a **linked list**.

All pairs $(k, v)$ whose key produces the same hash value $h(k) = i$ are inserted into the linked list attached to cell $H[i]$.

If a slot has no associated elements, its pointer is `NIL`.
