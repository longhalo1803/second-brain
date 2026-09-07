---
title: "Exercise 9 (2)"
tags:
  - dsa
  - flashcards
  - clrs
  - sorting
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "Exercise 9 (2)"
---

# 🎴 Exercise 9 (2)

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📝 Exercise 9

For each of the following cases indicate the content of array $C$ used by `Counting Sort` in the **non-stable** version AND in the **stable** one right before filling array $B$:

1. $A = \langle 2, 3, 5, 2, 1, 4, 5, 4, 6, 9, 5, 6, 7, 3, 6, 7, 7 \rangle$;
2. $A = \langle 2, 3, 4, 5, 6, 6, 7, 7, 7, 7, 8, 8, 8, 9, 2, 3, 4, 5, 6, 6, 6, 6, 7, 7, 7, 7, 8, 9 \rangle$;
3. $A = \langle 2, 3, 4, 5, 6, 6, 7, 7, 0, 7, 8, 0, 8, 8, 2, 3, 4, 5, 6, 1, 6, 6, 1, 7, 2, 7, 3, 8 \rangle$. #card
   ?
   **1. Sequence 1:**

- Non-stable version (frequencies): $C = \langle 0, 1, 2, 2, 2, 3, 3, 3, 0, 1 \rangle$
- Stable version (prefix sums): $C = \langle 0, 1, 3, 5, 7, 10, 13, 16, 16, 17 \rangle$**2. Sequence 2:**

- Non-stable version: $C = \langle 0, 0, 2, 2, 2, 2, 6, 8, 4, 2 \rangle$
- Stable version: $C = \langle 0, 0, 2, 4, 6, 8, 14, 22, 26, 28 \rangle$**3. Sequence 3:**

- Non-stable version: $C = \langle 2, 2, 3, 3, 2, 2, 5, 5, 4 \rangle$
- Stable version: $C = \langle 2, 4, 7, 10, 12, 14, 19, 24, 28 \rangle$
