---
title: "Describe the implementation of the Stack data structure using an array of size n w..."
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
  - "Describe the implementation of the Stack data structure using an array of size n w..."
---

# 🎴 Describe the implementation of the Stack data structure using an array of size n w...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 📝\* Describe the implementation of the Stack data structure using an array of size $n$ with an associated cursor, and provide the pseudocode for all primitives ($\textsf{new_stack}$, $\textsf{is_empty_stack}$, $\textsf{push}$, $\textsf{top}$, $\textsf{pop}$). #card

?
**Representation of the Stack $P$:**

- $P.S$: array of $n$ elements ($P.S[0..n-1]$).
- $P.top$: integer cursor to the top of the stack (index of the most recently inserted element).
- Empty stack: $P.top = -1$.
- Full stack: $P.top = n - 1$.
  **Assumptions:** it is not possible to insert into a full stack nor delete from an empty stack.

\*\*Pseudocode of primitives:

1. Stack creation (**$\textsf{new_stack}$**):\*\* returns a new empty stack

```text
{aligned}                            // new_stack(n)
    // P := new_stack_node()
    // P.top := -1
    // P.S := new_array[0..n-1]
    // return P {aligned}
```

**2. Empty stack test ($\textsf{is_empty_stack}$): **returns True if the stack contains no values, False otherwise (when the stack is empty we have `P.top = -1`)

```text
{aligned}                            // is_empty_stack(P)
    // return (P.top = -1) {aligned}
```

**Full stack test\*\*** ($\textsf{is_full_stack}$)\*\*: returns True if the stack cannot contain more values, False otherwise (when the stack is full we have `P.top = n-1`)

```text
{aligned}                            // is_full_stack(P)
    // return (P.top = n-1) {aligned}
```

**3. Insertion ($\textsf{push}$): **inserting a value at the top

```text
{aligned}                            // push(P, x)
    // n := length(P.S)
    // if P.top  -1 then
        // return P.S[P.top] {aligned}
```

**5. Extract top ($\textsf{pop}$): **returns the value at the top of the stack and removes it from the stack
_Version 1 (uses $\textsf{top}$):_

```text
{aligned}                            // pop(P)
    // if P.top > -1 then
        // x := top(P)
        // P.top := P.top - 1
        // return x {aligned}
```

_Version 2 (direct access):_

```text
{aligned}                            // pop(P)
    // if P.top > -1 then
        // P.top := P.top - 1
        // return P.S[P.top + 1] {aligned}
```

📌 Note: all primitives have a constant execution cost $O(1)$.
