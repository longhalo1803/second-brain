---
title: "How does the inner loop insertion mechanism work in InsertionSort"
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
  - "How does the inner loop insertion mechanism work in InsertionSort"
---

# 🎴 How does the inner loop insertion mechanism work in InsertionSort

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: How does the inner loop insertion mechanism work in InsertionSort? #card

?
**How do we put **$A[j]$** in the right place?**

- Save the value to be positioned in a temporary variable: $\textsf{tmp} := A[j]$.
- Compare $\textsf{tmp}$ with the sorted values on the left, starting at $i = j-1$ and moving leftwards ($i \to i-1$).
- If $A[i] > \textsf{tmp}$, we shift $A[i]$ to the right to position $i+1$ ($A[i+1] := A[i]$) to make room.
- We stop as soon as:
- We find an element $A[i] \le \textsf{tmp}$, or
- We reach the beginning of the array ($i = -1$).
- In both cases, we insert $\textsf{tmp}$ into the vacated position: $A[i+1] := \textsf{tmp}$.
