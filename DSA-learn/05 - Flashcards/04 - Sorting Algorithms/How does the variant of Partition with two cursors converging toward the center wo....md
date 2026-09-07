---
title: "How does the variant of Partition with two cursors converging toward the center wo..."
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
  - "How does the variant of Partition with two cursors converging toward the center wo..."
---

# 🎴 How does the variant of Partition with two cursors converging toward the center wo...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: How does the variant of `Partition` with two cursors converging toward the center work (_Hoare partition scheme_)? #card

?
It uses two indices/pointers $i$ and $j$ starting from opposite ends of the subarray and moving toward the center:

- The left pointer $i$ advances as long as it finds elements $\le \text{pivot}$.
- The right pointer $j$ moves backward as long as it finds elements $> \text{pivot}$.
- When both pointers stop on elements that are "out of place", these two elements are swapped.
- Both stop as soon as they encounter the first value that violates the rule!

- The algorithm terminates when the indices meet or cross each other.It guarantees that to the right of $j$ there are only elements $\ge \text{pivot}$ and to the left of $i$ there are only elements $\le \text{pivot}$.

📝 Example (pivot = 9):
