---
title: "Exercise 4 (2)"
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
  - "Exercise 4 (2)"
---

# 🎴 Exercise 4 (2)

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📝📍 Exercise 4

For each of the following cases, indicate on which subsequence of $A$ `MergeSort` is called at the $i$-th recursive call (also counting the main call):

1. $A = \langle 2, 3, 5, 2, 1, 4, 5, 4, 6, 9, 5, 6, 7, 3, 6, 7, 7 \rangle$ and $i=10$;

2. $A = \langle 2, 3, 4, 5, 6, 6, 7, 7, 7, 7, 8, 8, 8, 9, 2, 3, 4, 5, 6, 6, 6, 6, 7, 7, 7, 7, 8, 9 \rangle$ and $i=12$;

3. $A = \langle 2, 3, 4, 5, 6, 6, 7, 7, 7, 7, 8, 8, 8, 9, 2, 3, 4, 5, 6, 6, 6, 6, 7, 7, 7, 7, 8, 9 \rangle$ and $i=17$;

4. $\vert{}A\vert{}=20$ and $i=9$: indicate the first and last index of the subsequence;

5. $\vert{}A\vert{}=54$ and $i=28$: indicate the first and last index of the subsequence. #card
   ?

- $A[3] = \langle 2 \rangle$
- $A[4..5] = \langle 6, 6 \rangle$
- $A[7..10] = \langle 7, 7, 7, 8 \rangle$
- $A[3..4]$
- $A[12]$
  $\begin{array}{ll}\textsf{MergeSort(A, i, j)} & \\\quad \texttt{if } \textsf{i} Show steps

```text
{aligned} Call 1:                    // [0..19] k = floor( (0+19) / 2 ) = 9 (Left: [0..9], Right: [10..19])
            Call 2:                              // {{red}{[0..9]}}_{Left branch} k = floor( (0+9) / 2 ) = 4 (Left: [0..4], Right: [5..9])
            Call 3:                              // {{red}{[0..4]}}_{Left branch} k = floor( (0+4) / 2 ) = 2 (Left: [0..2], Right: [3..4])
            Call 4:                              // {{red}{[0..2]}}_{Left branch} k = floor( (0+2) / 2 ) = 1 (Left: [0..1], Right: [2..2])
            Call 5:                              // {{red}{[0..1]}}_{Left branch} k = floor( (0+1) / 2 ) = 0 (Left: [0..0], Right: [1..1])
    Call 6:                              // {{green}{[0..0]}}_{Left base case} Returns
    Call 7:                              // {{blue}{[1..1]}}_{Right base case of 5} Returns
    Call 8:                              // {{blue}{[2..2]}}_{Right base case of 4} Returns
    Call 9:                              // {{blue}{[3..4]}}_{Right branch of 3} {green}{A[3..4]} {aligned}
```

📌 Explanation ex. 5:
A subtree of size $N$ generates exactly $2N - 1$ calls. We exploit this rule to skip whole blocks:

Show steps

```text
{aligned} Call 1:                    // [0..53] k = 26 (Left: [0..26], Right: [27..53])
    // Left: 27 elements 53 calls (contains the 28th)
        Call 2:                              // {{red}{[0..26]}}_{Left branch} k = 13 (Left: [0..13], Right: [14..26])
    // Left: 14 elements 27 calls (3..29)
        Call 3:                              // {{red}{[0..13]}}_{Left branch} k = 6 (Left: [0..6], Right: [7..13])
    // Left: 7 elements 13 calls (4..16) passes to Right [7..13]
        Call 17:                             // {{blue}{[7..13]}}_{Right branch} k = 10 (Left: [7..10], Right: [11..13])
    // Left: 4 elements 7 calls (18..24) passes to Right [11..13]
        Call 25:                             // {{blue}{[11..13]}}_{Right branch} k = 12 (Left: [11..12], Right: [13..13])
    // Left: 2 elements 3 calls (26..28)
        Call 26:                             // {{red}{[11..12]}}_{Left branch} k = 11 (Left: [11..11], Right: [12..12])
    Call 27:                             // {{green}{[11..11]}}_{Left base case} Returns
    Call 28:                             // {{green}{[12..12]}}_{Right base case} {green}{A[12]} {aligned}
```
