---
title: "Exercise 1 - Longest Increasing Subsequence"
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
  - "Exercise 1 - Longest Increasing Subsequence"
---

# 🎴 Exercise 1 - Longest Increasing Subsequence

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: 📝📍 Exercise 1 - Longest Increasing Subsequence**

**For each of the sequences given below, write the content of array $L$, which stores all the Longest Increasing Subsequences computed by the dynamic programming algorithm.

**(a)** $A = \langle 29, 35, 35, 18, 23, 4, 8, 7, 34, 9, 13, 1 \rangle$
**(b)** $A = \langle 15, 24, 13, 23, 5, 35, 15, 15, 9, 9, 11, 2 \rangle$
**(c)** $A = \langle 1, 25, 12, 5, 6, 17, 1, 28, 22, 18, 27, 20 \rangle$
**(d)** $A = \langle 32, 35, 11, 12, 4, 35, 27, 11, 22, 7, 27, 36 \rangle$
**(e)** $A = \langle 26, 8, 28, 24, 15, 28, 36, 11, 6, 5, 18, 10 \rangle$
**(f)** $A = \langle 18, 33, 7, 33, 17, 29, 16, 35, 20, 26, 16, 5 \rangle$
**(g)** $A = \langle 13, 34, 11, 13, 21, 18, 27, 14, 31, 19, 31, 4 \rangle$ #card
?
**(a)** $L = [1, 2, 2, 1, 2, 1, 2, 2, 3, 3, 4, 1]$
**(b)** $L = [1, 2, 1, 2, 1, 3, 2, 2, 2, 2, 3, 1]$
**(c) **$L = [1, 2, 2, 2, 3, 4, 1, 5, 5, 5, 6, 6]$
**(d)**  $L = [1, 2, 1, 2, 1, 3, 3, 2, 3, 2, 4, 5]$
**(e)** $L = [1, 1, 2, 2, 2, 3, 4, 2, 1, 1, 3, 2]$
**(f)** $L = [1, 2, 1, 2, 2, 3, 2, 4, 3, 4, 2, 1]$
**(g)** $L = [1, 2, 1, 2, 3, 3, 4, 3, 5, 4, 5, 1]$

📌 Explanation for (a):

$$

A = \langle \overset{1}{29}, \overset{2}{35}, \overset{3}{35}, \overset{4}{18}, \overset{5}{23}, \overset{6}{4}, \overset{7}{8}, \overset{8}{7}, \overset{9}{34}, \overset{10}{9}, \overset{11}{13}, \overset{12}{1} \rangle

$$

$\boxed{L[j] = \max_{i < j, A[i] < A[j]} \{ L[i] \} + 1 }$

(*if there are no preceding elements smaller than _$A[j]$_, set *$L[j] = 1$).

```text
{aligned} L[1]                       // = 1 (no preceding elements)
L[2]                                 // = (L[1]) + 1 = 2
L[3]                                 // = (L[1]) + 1 = 2
    L[4]                                 // = 1 (no preceding element < 18)
L[5]                                 // = (L[4]) + 1 = 2
L[6]                                 // = 1
L[7]                                 // = (L[6]) + 1 = 2
L[8]                                 // = (L[6]) + 1 = 2
L[9]                                 // = (L[1], L[4], L[5], L[6], L[7], L[8]) + 1 = 3
L[10]                                // = (L[6], L[7], L[8]) + 1 = 3
L[11]                                // = ({L[6], L[7], L[8], L[10]}_{ elements < \; A[11]=13}) + 1 = {red}{{4}}
L[12]                                // = 1 {aligned}
```

Result: $L = [1, 2, 2, 1, 2, 1, 2, 2, 3, 3, 4, 1]$

The maximum length of the LIS is $\max(L) = \color{red}\mathbf{4}$ (reached at $L[11]$).

An optimal subsequence is obtained by reconstructing backwards from $j=11$:

```text
4, 8, 9, 13 or 4, 7, 9, 13
```
