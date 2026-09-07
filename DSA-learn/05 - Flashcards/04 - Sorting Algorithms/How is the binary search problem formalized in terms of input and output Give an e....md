---
title: "How is the binary search problem formalized in terms of input and output Give an e..."
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
  - "How is the binary search problem formalized in terms of input and output Give an e..."
---

# 🎴 How is the binary search problem formalized in terms of input and output Give an e...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: How is the **binary search** problem formalized in terms of input and output? Give an example. #card

?
**INPUT:**

- A **sorted** sequence of $n$ elements stored in an array $L$:
  $L[0] \le L[1] \le L[2] \le \dots \le L[n-2] \le L[n-1]$
- A key element $key$ of the same type as the elements in $L$.

**OUTPUT:**

- The **position** (index) of $key$ in $L$ if $key$ is present, $-1$ otherwise.

📝 **Example:**
If $L = \langle 1, 3, 5, 6, 9, 12, 23, 56, 78, 91, 125, 140 \rangle$:

- With $key = 12$, the output is $5$.
- With $key = 10$, the output is $-1$.
