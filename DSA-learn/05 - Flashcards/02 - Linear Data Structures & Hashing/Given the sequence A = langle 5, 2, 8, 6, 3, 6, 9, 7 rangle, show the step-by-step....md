---
title: "Given the sequence A = langle 5, 2, 8, 6, 3, 6, 9, 7 rangle, show the step-by-step..."
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
  - "Given the sequence A = langle 5, 2, 8, 6, 3, 6, 9, 7 rangle, show the step-by-step..."
---

# 🎴 Given the sequence A = langle 5, 2, 8, 6, 3, 6, 9, 7 rangle, show the step-by-step...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: 📝 Given the sequence $A = \langle 5, 2, 8, 6, 3, 6, 9, 7 \rangle$, show the step-by-step trace of the array $L[1..8]$. #card

?
We apply the formula $L[j] = \max_{i **j**12345678**A[j]**52863697**L[j]**11222344
**Calculations performed:**

- $L[1]$ ($a_1 = 5$): there are no previous elements, so the subsequence grows only from itself $\rightarrow L[1] = 1$.
- $L[2]$ ($a_2 = 2$): the only previous element is $a_1 = 5$, which is greater than 2. Since there are no previous elements smaller than 2, nothing can be extended $\rightarrow L[2] = 1$.
- $L[3]$ ($a_3 = 8$): The previous elements smaller than 8 are both $a_1 = 5$ and $a_2 = 2$ → $\max(L[1], L[2]) + 1 = \max(1, 1) + 1 = 2$.
- **$L[4]$ ($a_4=6$):** $\max(L[1], L[2]) + 1 = \max(1, 1) + 1 = 2$.
- **$L[5]$ ($a_5=3$):** $\max(L[2]) + 1 = 1 + 1 = 2$.
- **$L[6]$ ($a_6=6$):** $\max(L[1], L[2], L[5]) + 1 = \max(1, 1, 2) + 1 = 3$.
- **$L[8]$ ($a_8=7$):** $\max(L[6], L[5], L[4], L[3], L[2], L[1]) + 1 = \max(3, 2, 2, 2, 1, 1) + 1 = 4$.Maximum length of the LIS: $\max(L) = 4$.
