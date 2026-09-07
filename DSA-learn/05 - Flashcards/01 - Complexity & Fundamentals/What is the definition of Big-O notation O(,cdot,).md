---
title: "What is the definition of Big-O notation O(,cdot,)"
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
  - "What is the definition of Big-O notation O(,cdot,)"
---

# 🎴 What is the definition of Big-O notation O(,cdot,)

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: What is the definition of Big-O notation $O(\,\cdot\,)$? #card

?
Given two functions $f,g : \mathbb{N} \to \mathbb{R}^+$, we say that:

```text
f(n) ∈ O(g(n)) c > 0, \, n_0 ∈ {N} : [rgb]{0.047,0.565,0.933}{f(n) ≤q c g(n)} n ≥q n_0
```

**Intuition:** from a certain point onward, $f(n)$ **_never lies above_** $c g(n)$ (_asymptotic upper bound_).

📝 Examples: $\log n \in O(\sqrt n), \quad n^3 \in O(2^n), \quad 100 \cdot n^2 \in O(n^3), \quad 10^n \in O(n!)$.
📝 Example proof:  
Let $f(n) = 3n^2 + 4n + 5$ and $g(n) = n^2$.
Let us prove that

$$
3n^2 + 4n + 5 \in O(n^2)
$$

that is, show that there exist two constants $c>0$ and $n_0 \in \mathbb{N}$ (to be found) such that $\forall n \geq n_0$ it holds that

$$
3n^2 + 4n + 5 \leq n^2
$$

We replace each term with a multiple of $n^2$ and find the $n_0$ for which the inequality holds.
Comparing lower-degree terms ($4n$ and $5$) with $n^2$, we have that for $n=3$ and above, $4n\leq 4n^2, \; 5\leq n^2$ hold, so for $n \geq 3$:

$$
3n^2 + 4n + 5 \leq 3n^2 + 4n^2 + n^2 = 8n^2
$$

($3n^2 + 4n + 5 \leq 3n^2 + 4n^2 + \textcolor{orange}5n^2 = 12n^2 \implies c=12, n_0=1$ is also fine, even if slightly less "optimized". It is sufficient to find at least one valid pair of those two values.)
Therefore, with $c=8, n_0=3$ we have $f(n) \in O(n^2)$.

📌 Note: constants are not necessarily unique, but finding one pair is sufficient.
