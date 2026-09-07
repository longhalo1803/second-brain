---
title: "What is the summary comparison of computational costs (in asymptotic notation) for..."
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
  - "What is the summary comparison of computational costs (in asymptotic notation) for..."
---

# 🎴 What is the summary comparison of computational costs (in asymptotic notation) for...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: What is the summary comparison of computational costs (in asymptotic notation) for the main operations on Lists, Stacks, and Queues? #card

?
Here is the comparison table of computational costs:

Structure / OperationAt Head / TopAt Tail / BackArbitrary position $i$ / Search**Linked List**$\Theta(1)$ (`insert_head`)$\Theta(n)$ (without tail)$\Theta(i)$ / $\Theta(n)$ (`search`, `delete`)**Stack (on List)**$\Theta(1)$ (`push`, `pop`, `top`)N/AN/A (LIFO access only)**Queue (on List with head+tail)**$\Theta(1)$ (`dequeue`, `first`)$\Theta(1)$ (`enqueue`)N/A (FIFO access only)**Circular Array (Queue)**$\Theta(1)$$\Theta(1)$N/A
