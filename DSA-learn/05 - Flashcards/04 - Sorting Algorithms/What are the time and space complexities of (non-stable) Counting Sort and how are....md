---
title: "What are the time and space complexities of (non-stable) Counting Sort and how are..."
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
  - "What are the time and space complexities of (non-stable) Counting Sort and how are..."
---

# 🎴 What are the time and space complexities of (non-stable) Counting Sort and how are...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What are the time and space complexities of (non-stable) Counting Sort and how are the cost components broken down? #card

?
**Time Complexity:** $T(n) \in \Theta(n + k)$
The total time is broken down as follows:

- Initialization of $C[0 .. k]$: $\Theta(k)$
- Counting occurrences by scanning $A$: $\Theta(n)$
- Loops for populating $A$: the outer `for` loop performs $k+1$ checks and the inner `while` loop performs in total exactly $n$ assignments $\implies \Theta(n + k)$

$$
T(n) \in \Theta(k) + \Theta(n) + \Theta(n + k) = \Theta(n + k)
$$

**Auxiliary Space Complexity:** $\Theta(k)$
Allocates only a single auxiliary array $C$ of size $k+1$.
