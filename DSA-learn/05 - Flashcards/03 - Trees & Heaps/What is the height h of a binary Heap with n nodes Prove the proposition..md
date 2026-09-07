---
title: "What is the height h of a binary Heap with n nodes Prove the proposition."
tags:
  - dsa
  - flashcards
  - clrs
  - trees-heaps
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "What is the height h of a binary Heap with n nodes Prove the proposition."
---

# 🎴 What is the height h of a binary Heap with n nodes Prove the proposition.

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What is the height $h$ of a binary Heap with $n$ nodes? Prove the proposition. #card

?
**Proposition**: A binary Heap with $n$ nodes has height

$$

h = \lfloor \log_2 n \rfloor

$$

**Proof**:
Recalling that a complete and perfectly balanced binary tree of height $h$ has exactly $2^{h+1}-1$ nodes:

- A heap of height $h$ has at least as many nodes as a complete tree of height $h-1$, plus 1 node at level $h$:

$$

n > 2^{(h-1)+1}-1 = 2^h - 1 \implies n \ge 2^h

$$

- A heap of height $h$ cannot have more nodes than a complete tree of height $h$:

$$

n \le 2^{h+1} - 1 \implies n < 2^{h+1}

$$

Combining the two inequalities we get:

$$

2^h \le n < 2^{h+1} \iff h \le \log_2 n < h+1

$$

Since the height $h$ must be an integer, it follows that $h = \lfloor \log_2 n \rfloor$.

📝 Example:
If $n = 12$, then $h = \lfloor \log_2 12 \rfloor = 3$.
