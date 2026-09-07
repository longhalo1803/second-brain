---
title: "How does the Multiplication Method work"
tags:
  - dsa
  - flashcards
  - clrs
  - data-structures
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "How does the Multiplication Method work"
---

# 🎴 How does the Multiplication Method work

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: How does the **Multiplication Method** work? #card

?
The multiplication method operates in two steps: given a real constant $A$ with $0 < A < 1$, compute:

$$

h(k) = \lfloor m \cdot (A \cdot k - \lfloor A \cdot k \rfloor) \rfloor

$$

**Computation steps:**

- Multiply key $k$ by constant $A$.
- The expression $(A \cdot k - \lfloor A \cdot k \rfloor)$ **isolates the fractional (decimal) part** of $A \cdot k$.
- Multiply this fractional part by the table size $m$.
- Apply the floor function $\lfloor \dots \rfloor$ to yield an integer index between $0$ and $m-1$.**Fundamental advantage:** the choice of $m$ is **not critical** for distribution quality; it is typically convenient to choose $m = 2^p$ to allow efficient binary computation.
