---
title: "Show a practical example of reconstructing the LIS using the prev array for the se..."
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
  - "Show a practical example of reconstructing the LIS using the prev array for the se..."
---

# 🎴 Show a practical example of reconstructing the LIS using the prev array for the se...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: Show a practical example of reconstructing the LIS using the `prev` array for the sequence $A = \langle 5, 2, 8, 6, 3, 6, 9, 7 \rangle$. #card

?
Given the arrays computed by the algorithm:
**j**12345678**A[j]**52863697**L[j]**11222344**prev[j]**00112566
**Reconstruction trace:**

1. The maximum value in $L$ is $4$, reached at $k = 8$ (or $k = 7$). Let's select $k = 8$ ($A[8] = 7$).
2. `push(lis, A[8])` $\to$ pushes **7**. New $k = prev[8] = 6$.
3. `push(lis, A[6])` $\to$ pushes **6**. New $k = prev[6] = 5$.
4. `push(lis, A[5])` $\to$ pushes **3**. New $k = prev[5] = 2$.
5. `push(lis, A[2])` $\to$ pushes **2**. New $k = prev[2] = 0$ $\to$ **STOP**.

**Result (by popping the stack):** LIS subsequence = $\langle 2, 3, 6, 7 \rangle$ (length 4).
