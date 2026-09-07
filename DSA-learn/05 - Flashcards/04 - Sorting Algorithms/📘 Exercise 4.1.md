---
title: "📘 Exercise 4.1"
tags:
  - dsa
  - flashcards
  - clrs
  - sorting
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "📘 Exercise 4.1"
---

# 🎴 📘 Exercise 4.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📘 Exercise 4.1

**Input:** A queue $Q$ containing integers sorted in non-increasing order (maximum at front, minimum at rear).
**Output:** A queue $Q'$ containing the same values sorted in non-decreasing order (minimum at front, maximum at rear).

- Explain an algorithm to solve the problem.
- Provide the pseudocode using exclusively high-level queue primitives: `new_queue()`, `is_empty_queue(Q)`, `enqueue(Q, val)`, `dequeue(Q)`.
- Analyze the computational complexity. #card
  ?
  **Reasoning:**
  To reverse a queue using only queue operations, we can utilize the LIFO nature of the call stack via recursion. As the recursive calls return, elements are enqueued in reverse order.

**1. Algorithm Description:**
Create an empty queue $Q'$. Define a recursive procedure that dequeues an element from $Q$, recursively empties the rest of $Q$, and then enqueues the saved element into $Q'$. The recursive unwind naturally reverses the order, placing elements in non-decreasing order into $Q'$.

**2. Pseudocode:**

```text
Algorithm ReverseSortedQueue(Q):
    Q' ≤ftarrow new_queue()
    ReverseHelper(Q, Q')
    return Q'

Procedure ReverseHelper(Q, Q'):
    if not is_empty_queue(Q) then
        x ≤ftarrow dequeue(Q)
        ReverseHelper(Q, Q')
        enqueue(Q', x)
```

**3. Complexity:**

- Time Complexity: $O(n)$, where $n$ is the number of elements in $Q$, as each element is dequeued and enqueued once.
- Space Complexity: $O(n)$ auxiliary space on the call stack.
