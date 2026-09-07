---
title: "Exercise 7"
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
  - "Exercise 7"
---

# 🎴 Exercise 7

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📝📍 Exercise 7

For each of the following cases, given the input sequence $A$, indicate how many comparisons `InsertionSort` performs:

1. $A = \langle 11, 6, 20, 11, 11, 20 \rangle$;
2. $A = \langle 4, 18, 4, 18, 19, 18 \rangle$;
3. $A = \langle 19, 10, 9, 19, 8, 12 \rangle$;
4. $A = \langle 2, 12, 18, 15, 7, 20 \rangle$. #card
   ?

- **$A = \langle 11, 6, 20, 11, 11, 20 \rangle$:**

- $j=1$ (elem 6): 1 comparison with 11 $\rightarrow$ 1
- $j=2$ (elem 20): 1 comparison with 11 $\rightarrow$ 1
- $j=3$ (elem 11): 1 comparison with 20, 1 comparison with 11 $\rightarrow$ 2
- $j=4$ (elem 11): 1 comparison with 20, 1 comparison with 11 $\rightarrow$ 2
- $j=5$ (elem 20): 1 comparison with 20 $\rightarrow$ 1**Total comparisons = 7** (don't forget the last one!).

(The arrows indicate the comparisons and any swaps, the orange bar on the arrows indicates that the comparison occurred but **not** the swap)

- **$A = \langle 4, 18, 4, 18, 19, 18 \rangle$:**
  **Total comparisons = 7**.

- **$A = \langle 19, 10, 9, 19, 8, 12 \rangle$:**
  **Total comparisons = 11**.

- **$A = \langle 2, 12, 18, 15, 7, 20 \rangle$:**
  **Total comparisons = 9**.
