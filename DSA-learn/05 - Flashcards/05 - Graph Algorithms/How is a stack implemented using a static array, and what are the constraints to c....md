---
title: "How is a stack implemented using a static array, and what are the constraints to c..."
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
  - "How is a stack implemented using a static array, and what are the constraints to c..."
---

# 🎴 How is a stack implemented using a static array, and what are the constraints to c...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 📝\* How is a stack implemented using a static array, and what are the constraints to consider? #card

?
A stack of maximum size $n$ can be implemented with:

- An array `P.S` of $n$ elements.
- A cursor/index `P.top` pointing to the cell of the top element of the stack.
  **Array organization:**

- The cell `P.S[0]` contains the oldest value (bottom of the stack).
- The cell `P.S[P.top]` contains the value at the top of the stack.
- If the stack is empty, set `P.top = -1`.
  **Boundary and error conditions:**

- **Stack Overflow:** attempt to perform `push` when the stack is full (`P.top = n - 1`). Requires an `is_stack_full(P)` primitive.
- **Stack Underflow:** attempt to perform `pop` or `top` when the stack is empty (`P.top = -1`).
  Now try to implement it (_see Exercises for solution_).
