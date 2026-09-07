---
title: "What is the difference between algorithm complexity and problem complexity"
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
  - "What is the difference between algorithm complexity and problem complexity"
---

# 🎴 What is the difference between algorithm complexity and problem complexity

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: What is the difference between algorithm complexity and problem complexity? #card

?
**Algorithms**:
The cost (or complexity) of an algorithm's implementation measures the order of magnitude of the time required for its execution, typically in the worst case:$O(f(n))$ = upper bound (no input of size $n$ causes the algorithm to cost *more *than $f(n)$),
$\Omega(f(n))$ = lower bound (there exists at least one input that causes the algorithm to cost _at least _$f(n)$),
$\Theta(f(n))$ = tight bound (cost is exactly of the order of $f(n)$).

**Problems**:
The cost of a problem measures the intrinsic difficulty of solving it, independently of the algorithm used:$O(f(n))$ = cost of the best-known algorithm for the problem,
$\Omega(f(n))$ = proof that no algorithm can do better than $\Omega(f(n))$ in the worst case,
$\Theta(f(n))$ = an _optimal_ algorithm exists.

If the complexity of the algorithm (the implementation cost) matches the intrinsic complexity of the problem (the minimum necessary cost), the algorithm is called "**_optimal_**".
