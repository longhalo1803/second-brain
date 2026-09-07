---
title: "[REFERENCE] What are the values of the following summations"
tags:
  - dsa
  - flashcards
  - clrs
  - complexity
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "[REFERENCE] What are the values of the following summations"
---

# 🎴 [REFERENCE] What are the values of the following summations

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: [REFERENCE] What are the values of the following summations?

````text
_{i=1}^{n}i, _{i=1}^{n}i^{2}, _{i=0}^{n}x^{i}
``` #card
?
$\bullet$ Sum of the first $n$ natural numbers:

$$
\sum_{i=1}^{n}i=\frac{n(n+1)}{2}\in\Theta(n^{2}).
$$


Proof of Gauss's formula for the sum of the first $n$ natural numbers
  Consider the sum: $S_n = 1 + 2 + 3 + \dots + (n-1) + n$

We write the same sum in reverse order: $S_n = n + (n-1) + (n-2) + \dots + 2 + 1$

Adding the two expressions term by term: $2S_n = (1+n) + (2+n-1) + (3+n-2) + \dots + (n-1+2) + (n+1)$

Note that each pair in parentheses equals $n+1$. Since there are $n$ terms, we get: $2S_n = n(n+1)$

Dividing both sides by $2$: $\boxed{S_n = \frac{n(n+1)}{2}}$



  $\bullet$ Sum of the first $n$ squares:

$$
\sum_{i=1}^{n}i^{2}=\frac{n(n+1)(2n+1)}{6}\in\Theta(n^{3}).
$$

$\bullet$ $n$-th partial sum of the geometric series: for $x\ne1$ we have

$$
\sum_{i=0}^{n}x^{i}=\frac{1-x^{n+1}}{1-x}.
$$

In particular:
- When $01$ we have

$$
\sum_{i=0}^{n}x^{i}=\frac{1-x^{n+1}}{1-x}=\frac{1}{x-1}(x^{n+1}-1)\in\Theta(x^{n}).
$$
````
