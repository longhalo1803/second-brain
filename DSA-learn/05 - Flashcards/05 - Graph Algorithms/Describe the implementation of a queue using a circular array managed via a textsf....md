---
title: "Describe the implementation of a queue using a circular array managed via a textsf..."
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
  - "Describe the implementation of a queue using a circular array managed via a textsf..."
---

# 🎴 Describe the implementation of a queue using a circular array managed via a textsf...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 📝\* Describe the implementation of a queue using a circular array managed via a $\textsf{head}$ cursor and a $\textsf{dim}$ counter (Version 2). Provide the pseudocode for all primitives. #card

?
**Representation of the queue $C$ (Version 2):**

- $C.Q$: circular array of $n$ elements ($C.Q[0..n-1]$).
- $C.head$: index of the cell containing the head of the queue.
- $C.dim$: number of elements currently present in the queue.
- **Empty queue:** $C.dim = 0$.
- **Full queue:** $C.dim = n$.
- **Computation of the Tail:** The index for inserting at the tail is computed directly as $(\textsf{head} + \textsf{dim}) \bmod n$.
  **Pseudocode of primitives:**

**1. Queue creation ($\textsf{new_queue}$) and Empty test ($\textsf{is_empty_queue}$):**

```text
{aligned}                            // new_queue(n)
    // C := new_queue_node()
        // C.head := -1; C.dim := 0
    // C.Q := new_array[0..n-1]
    // return C
// is_empty_queue(C)
    // return (C.dim = 0) {aligned}
```

**2. Insertion ($\textsf{enqueue}$):**

```text
{aligned}                            // enqueue(C, x)
    // n := length(C.Q)
    // if C.dim  0 then return C.Q[C.head]
// dequeue(C)
    // n := length(C.Q)
    // if C.dim > 0 then
        // x := C.Q[C.head]
        // C.head := (C.head + 1) n
        // C.dim := C.dim - 1
        // return x {aligned}
```

📌 Note: compared to Version 1, the use of the $\textsf{dim}$ variable simplifies the empty/full tests and the handling of cursor resets when the queue becomes empty.
