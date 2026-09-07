---
title: "What is the relationship between polynomials and Big-O"
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
  - "What is the relationship between polynomials and Big-O"
---

# 🎴 What is the relationship between polynomials and Big-O

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: What is the relationship between polynomials and Big-O? #card

?
For every constant $k \geq 1$ we have

$$
a_k n^k + a_{k-1} n^{k-1} + \dots + a_1 n + a_0 = O(n^k)
$$

That is, every polynomial of maximum degree $k$ is $O(n^k)$.
In other words, every polynomial of maximum degree $k$ grows at most like the monomial $n^k$, up to a multiplicative constant: the term with the highest exponent ($n^k$) completely dominates the asymptotic growth of the entire polynomial, rendering all other lower-degree terms (such as $n^{k-1}, \dots, n, 1$) negligible.

**Proof**:
$\forall n \geq 0$ we have

$$
\begin{aligned}
& a_k n^k + a_{k-1} n^{k-1} + \dots + a_1 n + a_0 \\
& \leq |a_k| n^k + |a_{k-1}| n^{k-1} + \dots + |a_1| n + |a_0| \\
& \leq |a_k| n^k + |a_{k-1}| n^k + \dots + |a_1| n^k + |a_0| n^k \;\text{for }n>0 \\
& = \underbrace{(|a_k| + |a_{k-1}| + \dots + |a_1| + |a_0|)}_{c} n^k \\
& = cn^k
\end{aligned}
$$

📝 Example:

$$
f(n) = 6\textcolor{orange}{n^4} + 10n^2 + 3
$$

As $n$ grows, lower-degree terms become negligible:

$$
f(n) \leq (6+10+3) n^4 = 19n^4
$$

Thus $f(n) \in O(n^4)$.
