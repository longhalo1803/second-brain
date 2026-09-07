---
title: "Exercise 8"
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
  - "Exercise 8"
---

# 🎴 Exercise 8

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📝📍 Exercise 8

For each of the following cases state the sequence stored in $A$ after $k$ recursive calls of `Quicksort` (that is, stopping before call $k+1$ and including the main call).
Also indicate the sequence of pivots used and the sequence of subsequent $q$'s necessary to completely sort the sequence.

1. $A = \langle 4, 4, 8, 11, 19, 17, 18, 18, 3 \rangle$ and $k = 3$;
2. $A = \langle 6, 19, 16, 13, 11, 8, 13, 8, 18, 14 \rangle$ and $k = 4$;
3. $A = \langle 2, 17, 12, 6, 10, 8, 5, 6, 3, 13 \rangle$ and $k = 5$. #card
   ?

```text
QuickSort(A, p, r)
    if p  r$, it stops immediately without modifying the array.
- 3rd call ($p=1, r=8$, pivot 4 in the last position): uses 4 as pivot and at the end of the call the sequence becomes $A = \langle 3, 4, 4, 11, 19, 17, 18, 18, 8 \rangle$ with $q=2$.
- **Sequence stored after **$k=3$** calls:** $\langle 3, 4, 4, 11, 19, 17, 18, 18, 8 \rangle$.
- **Sequence of pivots used:** 3, 4, 8, 11, 19, 18, 18.
- **Sequence of **$q$'s: 0, 2, 3, 4, 8, 7, 6.
https://sammed05.github.io/interactive-uni-exercises/pages/Quicksort_Visualizer/?arr=4,4,8,11,19,17,18,18,3 (show Call Stack)

**2. Case 2 (**$A = \langle 6, 19, 16, 13, 11, 8, 13, 8, 18, 14 \rangle$**, **$k=4$**):**

- 1st call ($p=0, r=9$, pivot 14): after the main call the sequence is $A = \langle 6, 13, 11, 8, 13, 8, 14, 19, 18, 16 \rangle$ with $q=6$.
- 2nd call ($p=0, r=5$, pivot 8): uses 8 as pivot and at the end the sequence becomes $A = \langle 6, 8, 8, 13, 13, 11, 14, 19, 18, 16 \rangle$ with $q=2$.
- 3rd call ($p=0, r=1$, pivot 8): the call uses 8 as pivot and leaves the sequence unchanged with $q=1$.
- 4th call ($p=0, r=0$): made with $p = r$, so it does nothing and the sequence is not modified.
- **Sequence stored after **$k=4$** calls:** $\langle 6, 8, 8, 13, 13, 11, 14, 19, 18, 16 \rangle$.
- **Sequence of pivots used:** 14, 8, 8, 11, 13, 16, 19.
- **Sequence of **$q$'s: 6, 2, 1, 3, 5, 7, 9.

**3. Case 3 (**$A = \langle 2, 17, 12, 6, 10, 8, 5, 6, 3, 13 \rangle$**, **$k=5$**):**

- 1st call ($p=0, r=9$, pivot 13): after the main call we have $A = \langle 2, 12, 6, 10, 8, 5, 6, 3, 13, 17 \rangle$ with $q=8$.
- 2nd call ($p=0, r=7$, pivot 3): at the end of the call we have $A = \langle 2, 3, 6, 10, 8, 5, 6, 12, 13, 17 \rangle$ with $q=1$.
- 3rd call ($p=0, r=0$): made with $p = r$, does nothing and does not modify the sequence.
- 4th call ($p=2, r=7$, pivot 12): leaves the sequence unchanged with $q=7$.
- 5th call ($p=2, r=6$, pivot 6): the result of the partition is $A = \langle 2, 3, 6, 5, 6, 10, 8, 12, 13, 17 \rangle$ with $q=4$.
- **Sequence stored after **$k=5$** calls:** $\langle 2, 3, 6, 5, 6, 10, 8, 12, 13, 17 \rangle$.
- **Sequence of pivots used:** 13, 3, 12, 6, 5, 8.
- **Sequence of **$q$'s: 8, 1, 7, 4, 2, 5.
```
