---
title: "Describe the implementation of a queue using a circular array with textsf{head} an..."
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
  - "Describe the implementation of a queue using a circular array with textsf{head} an..."
---

# 🎴 Describe the implementation of a queue using a circular array with textsf{head} an...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 📝\* Describe the implementation of a queue using a circular array with $\textsf{head}$ and $\textsf{tail}$ cursors (Version 1). State the empty and full queue conditions and provide the pseudocode for all primitives. #card

?
**Representation of the queue $C$ (Version 1):**

- $C.Q$: circular array of $n$ elements ($C.Q[0..n-1]$).
- $C.head$: index of the cell containing the head value (the oldest).
- $C.tail$: index of the cell containing the tail value (the most recent).
- Circular update of cursors: calculated using the formula $(i \pm 1) \bmod n$.
- **Empty queue:** $C.head = -1$ and $C.tail = -1$.
- **Full queue:** $(C.tail + 1) \bmod n = C.head$ (the $\textsf{tail}$ immediately precedes the $\textsf{head}$).
  **Pseudocode of primitives:**

**1. Queue creation ($\textsf{new_queue}$):**

```text
{aligned}                            // new_queue(n)
    // C := new_queue_node()
        // C.head := -1; C.tail := -1
    // C.Q := new_array[0..n-1]
    // return C {aligned}
```

**2. Empty queue test ($\textsf{is_empty_queue}$) and full queue test ($\textsf{is_full_queue}$):**

```text
{aligned}                            // is_empty_queue(C)
    // return (C.head = -1)
// is_full_queue(C)
    // n := length(C.Q)
    // return ((C.tail + 1) n = C.head) {aligned}
```

**3. Insertion ($\textsf{enqueue}$):**

```text
{aligned}                            // enqueue(C, x)
    // n := length(C.Q)
    // if NOT is_full_queue(C) then
        // C.tail := (C.tail + 1) n
        // C.Q[C.tail] := x
        // if C.head = -1 then C.head := C.tail {aligned}
```

**4. Read first element ($\textsf{first}$) and Extraction ($\textsf{dequeue}$):**

```text
{aligned}                            // first(C)
    // if C.head > -1 then return C.Q[C.head]
// dequeue(C)
    // n := length(C.Q)
    // if C.head > -1 then
        // x := C.Q[C.head]
            // if C.head = C.tail then // the queue has become empty
                // C.head := -1; C.tail := -1
        // else
            // C.head := (C.head + 1) n
        // return x {aligned}
```

📌 Note: all primitives run in constant time $O(1)$.
