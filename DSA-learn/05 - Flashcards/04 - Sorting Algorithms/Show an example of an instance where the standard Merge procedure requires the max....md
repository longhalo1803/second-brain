---
title: "Show an example of an instance where the standard Merge procedure requires the max..."
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
  - "Show an example of an instance where the standard Merge procedure requires the max..."
---

# 🎴 Show an example of an instance where the standard Merge procedure requires the max...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: Show an example of an instance where the standard Merge procedure requires the maximum number of comparisons (j - i). [difficult] #card

?
In the worst case, the standard `Merge` procedure performs exactly $j - i$ comparisons when both indices `l` and `r` reach the last element of their respective sub-sequences before the `while` loop terminates.
The condition for having $j - i$ comparisons occurs for all instances in which the elements of the two portions are alternately interleaved, and specifically when:

```text
A[k-1]  A[j]
```

📝 Example:
Given the two sorted sub-arrays to be merged:

- Left sub-array $A[i \dots k]$: `` (with $k-1 \to 6$, $k \to 14$)
- Right sub-array $A[k+1 \dots j]$: `` (with $k+1 \to 7$, $j \to 12$)Step-by-step comparisons:

- The elements are compared and copied to $B$ in the following order: `2, 3, 4, 5, 6` (index `l` advances to point to `14`).
- Next, `14` is compared with the various elements on the right, copying to $B$: `7, 8, 9, 10, 11, 12` (index `r` advances past $j$).
- All elements except the last one (`14`) have been compared and extracted one by one. Index `r` exits the loop.Since the total size is $j - i + 1 = 6 + 6 = 12$, the number of comparisons performed in the `while` loop is exactly $12 - 1 = 11 = j - i$.
