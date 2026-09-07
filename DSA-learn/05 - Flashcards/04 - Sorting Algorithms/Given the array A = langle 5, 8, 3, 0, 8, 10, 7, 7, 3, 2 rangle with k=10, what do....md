---
title: "Given the array A = langle 5, 8, 3, 0, 8, 10, 7, 7, 3, 2 rangle with k=10, what do..."
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
  - "Given the array A = langle 5, 8, 3, 0, 8, 10, 7, 7, 3, 2 rangle with k=10, what do..."
---

# 🎴 Given the array A = langle 5, 8, 3, 0, 8, 10, 7, 7, 3, 2 rangle with k=10, what do...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: Given the array $A = \langle 5, 8, 3, 0, 8, 10, 7, 7, 3, 2 \rangle$ with $k=10$, what does the frequency array $C$ look like and which sorted sequence is generated? #card

?
We use an auxiliary array C, which must have as many cells as the possible values assumed by the elements in A, i.e., $k+1$.

_❓ Why *$k+1$*?
Let's look at a simpler example:
Remember that the CS algorithm assumes the elements inside array *$A$* are integers within the range *$[0, k]$*.
If the numbers in *$A$* range from *$0$* to *$k = 3$*, there are four possible values (_$0, 1, 2, 3$_), so *$C$* must have *$k + 1=4$* cells (indices *$0, 1, 2, 3$*)._
⚠️ Warning: the size of $C$ is always $k + 1$ (hence "1 more" than $k$, i.e., the maximum value of the range), not relative to the length of array $A$ ($n$). The two numbers $n$ and $k$ have no fixed relationship to each other.

$C[i]$ = number of occurrences in A of value $i$.

By scanning array $A$ and incrementing the cell corresponding to the read value ($C[A[j]] := C[A[j]] + 1$), we obtain the following auxiliary array $C$ of size 11 ($k+1$):

Index $i$012345678910$C[i]$10120102201
By scanning array $C$ and rewriting each value $i$ into $A$ for $C[i]$ times, we generate the sorted sequence:
$A = \langle 0, 2, 3, 3, 5, 7, 7, 8, 8, 10 \rangle$.

To fill C, we iterate through A and update C appropriately, and we generate the appropriate sequence in A by iterating through C:
