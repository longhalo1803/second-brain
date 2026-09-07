---
title: "What is the specification of the problem solved by the Merge procedure, and what i..."
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
  - "What is the specification of the problem solved by the Merge procedure, and what i..."
---

# 🎴 What is the specification of the problem solved by the Merge procedure, and what i...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What is the specification of the problem solved by the Merge procedure, and what is the basic idea of the algorithm? (no pseudocode) #card

?
**Problem solved by `Merge(A, i, k, j)`:**

- **Input:** two contiguous and already _sorted_ portions of array $A$: the first from $i$ to $k$ inclusive, the second from $k+1$ to $j$ inclusive.
- **Output:** the portion of array $A$ between indices $i$ and $j$ entirely _sorted_.

```text
\;\,INPUT {{0}{.........}\;}{[background: transparent; border: 1px solid #fff; padding: 8px 12px;]{{sorted}.........}} -1px {{i}{}{k\;}}{[background: #81C784; border: 1px solid #fff; border-left: none; border-right: 2px solid #000; padding: 8px 15px;]{sorted}} -1px {{\;k+1}{}{j}}{[background: #81C784; border: 1px solid #fff; border-left: none; padding: 8px 15px;]{sorted}} -1px {{.........}{n-1}}{[background: transparent; border: 1px solid #fff; border-left: none; padding: 8px 12px;]{{sorted}.........}\;}
                            [8pt] OUTPUT {{0}{.........}\;}{[background: transparent; border: 1px solid #fff; padding: 8px 12px;]{{sorted}.........}} -1px {{i}{\;\;\;}{j}}{[background: #81C784; border: 1px solid #fff; border-left: none; padding: 8px 3px;]{}} -1px {{\;.........}{n-1}}{[background: transparent; border: 1px solid #fff; border-left: none; padding: 8px 12px;]{{sorted}.........}}
```

**Operating idea (auxiliary array version):**

- An auxiliary temporary array $B[0 \dots j-i]$ of size $j-i+1$ is allocated.
- Three indices are used:
- `l` (left) to scan the left portion $A[i \dots k]$;
- `r` (right) to scan the right portion $A[k+1 \dots j]$;
- `t` to scan the auxiliary array $B[0 \dots j-i]$.
- At each step, the current elements $A[l]$ and $A[r]$ are compared: the smaller one is copied into $B[t]$, and the corresponding index (`l` or `r`) is incremented along with `t`.
- The process continues until one of the two portions is completely exhausted.
- **Handling remaining elements:**
- If the **left** portion is exhausted, the remaining elements on the right are already in their correct position in $A$.
- If the **right** portion is exhausted, the remaining elements on the left are the largest and must be relocated to the end of $A$.
- Finally, the sorted elements collected in $B$ are copied back into the original portion $A[i \dots i+t-1]$.
