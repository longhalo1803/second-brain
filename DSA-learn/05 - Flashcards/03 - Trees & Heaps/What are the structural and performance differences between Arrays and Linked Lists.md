---
title: "What are the structural and performance differences between Arrays and Linked Lists"
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
  - "What are the structural and performance differences between Arrays and Linked Lists"
---

# 🎴 What are the structural and performance differences between Arrays and Linked Lists

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What are the structural and performance differences between Arrays and Linked Lists? #card

?
**Array (**random access - static linear sequence**):**

- **Memory:** contiguous cells.

- **Access to the i-th element:** $\Theta(1)$ (calculated as $\text{position of first cell} + i$).

- **Insertion or deletion at head:** $O(n)$ (requires shifting all elements).
- See https://liveexample.pearsoncmg.com/dsanimation13ejava/ArrayListAnimationForTwo.html

**Linked List (**sequential access - dynamic linear sequence**):**

- **Memory:** non-contiguous cells connected by pointers.

- **Access to the i-th element:** $O(i)$ (requires sequential traversal starting from head).

- **Insertion or deletion at head:** $\Theta(1)$ (requires modifying pointers only).

📌 Note: the list is identified by the pointer to its first node (head), from which all subsequent elements can be reached.
