---
title: "What is a recursive function and what are its fundamental elements"
tags:
  - dsa
  - flashcards
  - clrs
  - dynamic-programming
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "What is a recursive function and what are its fundamental elements"
---

# 🎴 What is a recursive function and what are its fundamental elements

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: What is a **recursive function** and what are its fundamental elements? #card

?
A **recursive function** is a function that calls itself during its execution.

To work correctly and avoid infinite loops, it must have two fundamental elements:

- **Base cases**: conditions in which the function returns a result directly, _without_ calling itself.
- **Recursive cases**: conditions in which the function returns a result by calling itself, but with parameters _closer_ to the base cases (**thus solving a **subproblem** of smaller size**).📌 Note: recursion allows solving problems elegantly and with compact code.
