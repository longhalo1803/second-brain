---
title: "Show the step-by-step execution of InsertionSort on array A = langle 36, 14, 27, 4..."
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
  - "Show the step-by-step execution of InsertionSort on array A = langle 36, 14, 27, 4..."
---

# 🎴 Show the step-by-step execution of InsertionSort on array A = langle 36, 14, 27, 4...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📝 Show the step-by-step execution of InsertionSort on array $A = \langle 36, 14, 27, 40, 31 \rangle$ counting its comparisons #card

?

```text
InsertionSort(A, n)
    for j := 1 to n - 1 do
        i := j - 1
        tmp := A[j]
        while (i ≥ 0 AND A[i] > tmp) do
            A[i+1] := A[i]
            i := i - 1
        A[i+1] := tmp
```

**
Execution for** $A = \langle 36, 14, 27, 40, 31 \rangle$:

- **$j = 1, \textsf{tmp} = 14, i = 0$:**
  $A[0] = 36 > 14 \implies A[1] := 36, i := -1$. While condition false.
  Assigns $A[0] := 14$. Array: $\langle 14, 36, 27, 40, 31 \rangle$. (**1 comparison**)

- **$j = 2, \textsf{tmp} = 27, i = 1$:**
  $A[1] = 36 > 27 \implies A[2] := 36, i := 0$.
  $A[0] = 14 \le 27 \implies$ while condition false.
  Assigns $A[1] := 27$. Array: $\langle 14, 27, 36, 40, 31 \rangle$. (**2 comparisons**)

- **$j = 3, \textsf{tmp} = 40, i = 2$:**
  $A[2] = 36 \le 40 \implies$ while condition false on first attempt.
  Assigns $A[3] := 40$. Array: $\langle 14, 27, 36, 40, 31 \rangle$. (**1 comparison**)

- **$j = 4, \textsf{tmp} = 31, i = 3$:**
  $A[3] = 40 > 31 \implies A[4] := 40, i := 2$.
  $A[2] = 36 > 31 \implies A[3] := 36, i := 1$.
  $A[1] = 27 \le 31 \implies$ while condition false.
  Assigns $A[2] := 31$. Array: $\langle 14, 27, 31, 36, 40 \rangle$. (**3 comparisons**)
  **Total comparisons made:** $1 + 2 + 1 + 3 = 7$ comparisons.
