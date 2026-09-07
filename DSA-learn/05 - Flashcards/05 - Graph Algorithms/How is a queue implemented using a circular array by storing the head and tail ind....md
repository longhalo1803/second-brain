---
title: "How is a queue implemented using a circular array by storing the head and tail ind..."
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
  - "How is a queue implemented using a circular array by storing the head and tail ind..."
---

# 🎴 How is a queue implemented using a circular array by storing the head and tail ind...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 📝\* How is a queue implemented using a circular array by storing the head and tail indices (version 1)? #card

?
To avoid shifting all elements on every extraction, a **circular array** `C.Q` of size $n$ is used, where cell $0$ conceptually follows cell $n - 1$.

**Version 1 (`head` and `tail` indices):**

- `C.Q`: circular array of $n$ elements.
- `C.head`: index of the cell containing the head of the queue.
- `C.tail`: index of the cell containing the tail of the queue.
  **Circular arithmetic:**
  Indices advance circularly using the modulo operator:

$$
\text{next_index} = (\text{index} + 1) \bmod n
$$

⚠️ Warning: an `is_queue_full` primitive must be defined, and the empty queue condition must be clearly distinguished from the full queue condition to avoid overwriting elements.

Now try implementing it (_see Exercises for solution_).
