---
title: "What is a stack, what is its element access policy, and what are its primitives"
tags:
  - dsa
  - flashcards
  - clrs
  - graphs
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "What is a stack, what is its element access policy, and what are its primitives"
---

# 🎴 What is a stack, what is its element access policy, and what are its primitives

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: What is a stack, what is its element access policy, and what are its primitives? #card

?
A stack is a **sequential data structure** in which:

- The stored values are all of the same type.
- New values are added at the top (**PUSH** operation).
- An extraction always returns the last value inserted (**POP** operation).**Access policy:** **LIFO** (_Last In, First Out_ — the last one in is the first one out).

**Stack primitives:**

- `new_stack()`: creates a new empty stack.
- `is_empty_stack(S)`: checks if stack `S` is empty.
- `push(S, x)`: inserts value `x` onto the top of the stack.
- `top(S)`: returns the value at the top of the stack without removing it.
- `pop(S)`: extracts and removes the value at the top of the stack.
