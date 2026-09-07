---
title: "Determine the total number of comparisons performed by the Insertion Sort algorith..."
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
  - "Determine the total number of comparisons performed by the Insertion Sort algorith..."
---

# 🎴 Determine the total number of comparisons performed by the Insertion Sort algorith...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📝 Determine the total number of comparisons performed by the Insertion Sort algorithm to sort each of the following two arrays:

1. $A = \langle 11, 6, 20, 11, 11, 20 \rangle$
2. $B = \langle 4, 18, 4, 18, 19, 18 \rangle$ #card
   ?
   Detailed analysis and comparisons

**Analysis Array 1: $A = \langle 11, 6, 20, 11, 11, 20 \rangle$**

1. **Step $i = 1$ (key = 6):**

- Comparison between $A[1]$ (6) and $A[0]$ (11): $6

**Analysis Array 2: $B = \langle 4, 18, 4, 18, 19, 18 \rangle$**

1. **Step $i = 1$ (key = 18):**

- Comparison between $B[1]$ (18) and $B[0]$ (4): $18 \ge 4$, immediate stop.

- **Comparisons:** 1 (arrow $1 \to 0$)

- Array: $[4, 18, 4, 18, 19, 18]$

2. **Step $i = 2$ (key = 4):**

- Comparison between $B[2]$ (4) and $B[1]$ (18): $4
