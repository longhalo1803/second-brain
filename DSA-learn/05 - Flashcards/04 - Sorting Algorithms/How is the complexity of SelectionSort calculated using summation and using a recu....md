---
title: "How is the complexity of SelectionSort calculated using summation and using a recu..."
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
  - "How is the complexity of SelectionSort calculated using summation and using a recu..."
---

# 🎴 How is the complexity of SelectionSort calculated using summation and using a recu...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: How is the complexity of SelectionSort calculated using summation and using a recurrence relation?

Show algorithm code

```text
SelectionSort(A, i, n)
    if i #card
?
**1. Calculation via summation:**
The recursive procedure is invoked exactly once for each $i$ with $0 \le i \le n-2$. Summing the comparisons of `IndexOfMinimum` for each call:

$$
\begin{aligned}
T(n) &= \sum_{i=0}^{n-2} (n - 1 - i) = \sum_{i=0}^{n-2}(n-1) - \sum_{i=0}^{n-2} i \\
&= (n-1)(n-1) - \frac{(n-2)(n-1)}{2} = \frac{(n-1)n}{2} \in \Theta(n^2)
\end{aligned}
$$

**2. Calculation via recurrence relation:**
The base case has size $n=1$ with 0 comparisons (array already sorted).
For $n > 1$, there are $n-1$ comparisons (the first element with all others) for the minimum search (`IndexOfMinimum`) and a recursive cost of $T(n - 1)$ to sort the remaining $n - 1$ elements via the recursive call `SelectionSort(A, i + 1, n)`.

$$
T(n) = \begin{cases} 0 & \text{if } n = 1 \\ T(n - 1) + n - 1 & \text{otherwise} \end{cases}
$$

Unrolling the recurrence:

$$
\begin{aligned}  T(n) &= T(n-1) + n - 1 && \small\text{Initial formula} \\  &= \underbrace{[T(n-2) + n - 2]}_{T(n-1)} + n - 1 && \small\text{Expansion of } T(n-1) \\  &= \underbrace{[T(n-3) + n - 3]}_{T(n-2)} + n - 2 + n - 1 && \small\text{Expansion of } T(n-2) \\  &= \dots \\ &= T(n-k) + \sum_{i=n-k}^{n-1} i && \small\text{General form at step } k \\ &= \underbrace{T(1)}_{= 0} + (1 + 2 + \dots + n - 1) && \small\text{Setting } k = n - 1 \text{ (base case)} \\ &= \sum_{\substack{i=0 \\ \small\text{(or }i= 1)}}^{n-1} i && \small\text{Sum of the first } n-1 \text{ numbers} \\  &= \frac{(n-1)n}{2} \in \Theta(n^2) && \small\text{Gauss formula}  \end{aligned}
$$
```
