---
title: "Briefly explain in words how the SelectionSort sorting algorithm works and explain..."
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
  - "Briefly explain in words how the SelectionSort sorting algorithm works and explain..."
---

# 🎴 Briefly explain in words how the SelectionSort sorting algorithm works and explain...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: ❓ Briefly explain in words how the SelectionSort sorting algorithm works and explain why the number of element comparisons required to sort the sequence of values is quadratic in the number of values to sort. #card

?

- **Operation of SelectionSort:**
  The algorithm conceptually splits the array into two parts: an already sorted part on the left and an unsorted part on the right.
- At the start, the sorted part is empty.
- For each position $i$ from $0$ up to $n-2$:
- Scan the entire unsorted portion (from index $i+1$ up to $n-1$) to find the position of the minimum value.
- Once found, swap the minimum with the element at position $i$.
- Position $i$ becomes part of the sorted portion, and the algorithm moves to the next iteration.
- **Why the number of comparisons is quadratic:**
  The number of comparisons does not depend on the initial ordering of the data (the algorithm is non-adaptive).
- In the first iteration ($i=0$), finding the minimum among elements from $1$ to $n-1$ requires $n - 1$ comparisons.
- In the second iteration ($i=1$), it requires $n - 2$ comparisons.
- In the general iteration $i$, it requires $n - 1 - i$ comparisons, down to the last iteration which performs $1$ comparison. The total number of comparisons $C(n)$ is given by the sum of the first $n-1$ integers:

$$

C(n) = \sum*{i=0}^{n-2} (n - 1 - i) = \sum*{k=1}^{n-1} k = \frac{(n-1)n}{2} = \frac{n^2 - n}{2} = \Theta(n^2)

$$

Because the resulting function has $n^2$ as its dominant term, the number of comparisons is inherently quadratic in the best, average, and worst cases.
