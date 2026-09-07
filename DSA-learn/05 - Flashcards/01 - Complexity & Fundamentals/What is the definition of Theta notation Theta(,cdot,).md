---
title: "What is the definition of Theta notation Theta(,cdot,)"
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
  - "What is the definition of Theta notation Theta(,cdot,)"
---

# 🎴 What is the definition of Theta notation Theta(,cdot,)

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: What is the definition of "Theta" notation $\Theta(\,\cdot\,)$? #card

?
Given two functions $f,g : \mathbb{N} \to \mathbb{R}^+$, we say that:

$$
f(n) \in \Theta(g(n)) \iff \exists c_1,c_2 > 0, \, n_0 \in \mathbb{N} : c_1 g(n) \leq f(n) \leq c_2 g(n), \, \forall n \geq n_0
$$

**Intuition:** $f(n)$ grows like $g(n)$ up to constants. From a certain point onwards it lies between the functions $c_1g(n)$ and $c_2g(n)$.

📝 Example:
$f(n)=\textcolor{teal}{5n^2 + \log n}$.
We must prove that $f(n)$ is both $\Omega(n^2)$ and $O(n^2)$:

- Lower bound ($\Omega$): $\textcolor{teal}{5n^2 + \log n} \geq 5n^2 \quad \forall n \geq 1=n_0, c=5$ (_since log n ≥ 0 for n ≥ 1_)
- Upper bound ($O$): $\textcolor{teal}{5n^2 + \log n} \leq 5n^2 + n^2 \leq 6n^2 \quad \forall n \geq 1=n_0, c=6$ (_since log n ≤ n for every n ≥ 1_)
  $c_1=5, c_2=6, n_0=1$
  Therefore $f(n) \in \Theta(n^2)$.

See also https://opendsa-server.cs.vt.edu/ODSA/Books/CS3/html/AnalLower.html
