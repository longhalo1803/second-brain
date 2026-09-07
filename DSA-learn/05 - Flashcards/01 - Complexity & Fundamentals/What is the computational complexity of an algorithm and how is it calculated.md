---
title: "What is the computational complexity of an algorithm and how is it calculated"
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
  - "What is the computational complexity of an algorithm and how is it calculated"
---

# 🎴 What is the computational complexity of an algorithm and how is it calculated

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: What is the computational complexity of an algorithm and how is it calculated? #card

?
It is the order of magnitude (not the exact number) of operations performed by the algorithm for the **worst case **(worst case scenario) of the input, i.e., for the input instance that requires the largest number of instructions to produce the expected result.

📝 Example: suppose an algorithm takes $f(n) = 5n^2 + 3n + 2$ operations. We can say that
$f(n) \in O(n^2)$because there exists a constant $c$ (for example $c = 6$) such that
$f(n) \leq 6n^2 \quad \text{for } n \geq n_0$
📌 Note: $f(n) = O(g(n)) \iff f(n) \leq c\cdot g(n)$.
$n$ is the input size,
$c$ is a multiplicative constant that "adjusts" $g(n)$ so that it serves as an upper bound for $f(n)$.​
