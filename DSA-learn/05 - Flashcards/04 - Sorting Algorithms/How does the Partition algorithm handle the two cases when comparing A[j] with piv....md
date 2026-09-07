---
title: "How does the Partition algorithm handle the two cases when comparing A[j] with piv..."
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
  - "How does the Partition algorithm handle the two cases when comparing A[j] with piv..."
---

# 🎴 How does the Partition algorithm handle the two cases when comparing A[j] with piv...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: How does the `Partition` algorithm handle the two cases when comparing $A[j]$ with pivot $x$? #card

?
At each step of iteration $j$:

- **If **$A[j] > x$\*\* \*\*the element belongs to the $> x$ region. The index $i$ remains unchanged, and $j$ is incremented by 1 (no swap!).
- **If **$A[j] \le x$\*\* \*\*the element $A[j]$ is swapped with $A[i+1]$ (the first element of the $> x$ region), after which both $i$ and $j$ are incremented by 1.
