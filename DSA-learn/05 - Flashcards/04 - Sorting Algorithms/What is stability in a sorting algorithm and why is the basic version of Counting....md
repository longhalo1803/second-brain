---
title: "What is stability in a sorting algorithm and why is the basic version of Counting..."
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
  - "What is stability in a sorting algorithm and why is the basic version of Counting..."
---

# 🎴 What is stability in a sorting algorithm and why is the basic version of Counting...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What is stability in a sorting algorithm and why is the basic version of Counting Sort not stable? #card

?
A sorting algorithm is said to be **stable** if elements with the same value preserve in the sorted output array the same **relative order** they had in the starting sequence.

**Why basic Counting Sort is NOT stable:**
In the basic version, array $A$ is overwritten by regenerating values from scratch based on the frequencies counted in $C$. The original elements (and any information/data associated with them) are not placed while preserving their original position.

📝 Example:
If in the starting sequence we have two elements with value 2, say $2_a$ followed by $2_b$:

- In a **stable** algorithm: in the output, $\dots, 2_a, 2_b, \dots$ will appear
- In a **non-stable** algorithm: the relative order may invert ($\dots, 2_b, 2_a, \dots$) or the original elements are overwritten.

```text
{ {#E91E63}{{2}} {#2E7D32}{{2}} {#0088FF}{{2}} \;\,} A
            [1em] { {#E91E63}{{2}} \: {#2E7D32}{{2}} \: {#0088FF}{{2}} } stable
            [1em] { {#E91E63}{{2}} \: {#0088FF}{{2}} \: {#2E7D32}{{2}} } unstable
```

Equal values are found in the sorted sequence in the same order as they were in the starting sequence.
