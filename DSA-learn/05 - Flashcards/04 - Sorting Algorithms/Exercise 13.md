---
title: "Exercise 13"
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
  - "Exercise 13"
---

# 🎴 Exercise 13

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📝 Exercise 13

Consider the following sorting algorithm for a sequence $A$ of $n$ integers, each consisting of exactly $k \in \Theta(1)$ digits:
`For i from 0 to k-1:
  sort A with a stable algorithm based on the value of the digit at position i`

Recall that:
• The least significant digit (LSD) is the leftmost one and is located at position zero
• The most significant digit (MSD) is the rightmost one and is located at position $k-1$
• An algorithm is stable when equal values are found, in the final sorted sequence, in the same order as they were in the initial one.

Use the algorithm described above to sort the following sequence of numbers ($n=10, k=4$):
$A = \langle 2298, 2409, 4920, 4782, 7820, 4320, 2039, 2000, 7320, 5309 \rangle$, showing the state of the array at the start of each iteration.

Is the result obtained generalizable? Try to give an explanation of the result obtained. #card
?
**State of the array at the start of each iteration:**

- **Initial state (Start of iteration **$i=0$**, digit at pos. 0, leftmost):**
  $\langle 2298, 2409, 4920, 4782, 7820, 4320, 2039, 2000, 7320, 5309 \rangle$
- **Start of iteration **$i=1$** (after stable sort on pos. 0):**
  $\langle 2298, 2409, 2039, 2000, 4920, 4782, 4320, 5309, 7820, 7320 \rangle$
- **Start of iteration **$i=2$** (after stable sort on pos. 1):**
  $\langle 2039, 2000, 2298, 4320, 5309, 7320, 2409, 4782, 7820, 4920 \rangle$
- **Start of iteration **$i=3$** (after stable sort on pos. 2):**
  $\langle 2000, 5309, 2409, 4320, 7320, 7820, 4920, 2039, 4782, 2298 \rangle$
  **Final state of the array (after sort on pos. 3):**
  $\langle 2000, 4320, 7320, 7820, 4920, 4782, 2298, 5309, 2409, 2039 \rangle$

**Explanation and Generalizability of the result:**
The final array **is NOT sorted**.
The result is generalizable: in **`RadixSort` **the **least significant** digit (LSD) must be the units digit (rightmost) and the sorting must proceed from right to left up to the **most significant** digit (MSD).
In the exercise, position 0 was defined as the leftmost digit (MSD).
Sorting from left to right causes subsequent iterations on less significant digits to overwrite and destroy the order established on more significant digits in previous iterations, making the algorithm invalid if applied without recursive partitioning of subgroups.
