---
title: "What is the Open Addressing technique for collision handling"
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
  - "What is the Open Addressing technique for collision handling"
---

# 🎴 What is the Open Addressing technique for collision handling

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: What is the **Open Addressing** technique for collision handling? #card

?
In **open addressing**, all key-value pairs are stored **directly in the slots of array $H$**, without using linked lists or external auxiliary structures.

**Key features:**

- **Insertion:** an initial slot is computed; if that slot is already occupied, a sequence of **alternative slots** is systematically probed within the array until an empty slot is found.
- **Search:** starting from the base index, slots are examined following the exact same sequence until the target key is found or an empty slot is encountered (certifying that the key is absent).
- Each slot contains at most one element, so the load factor is strictly constrained by $0 \le \alpha \le 1$.
