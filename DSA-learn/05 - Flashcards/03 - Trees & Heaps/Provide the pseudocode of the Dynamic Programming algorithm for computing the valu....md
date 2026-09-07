---
title: "Provide the pseudocode of the Dynamic Programming algorithm for computing the valu..."
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
  - "Provide the pseudocode of the Dynamic Programming algorithm for computing the valu..."
---

# 🎴 Provide the pseudocode of the Dynamic Programming algorithm for computing the valu...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 🟢 Provide the pseudocode of the Dynamic Programming algorithm for computing the value in the Knapsack with repetition. #card

?
The pseudocode iteratively computes the table $K[0 .. W]$:

```text
Knapsack_With_Repetition(W, n, w, v) // W: total capacity, n: num. items
    min := _{i ∈ [1..n]} { w_i }         // minimum weight among items
    for w := 0 to min - 1 do             // for capacities less than minimum weight
        K[w] := 0                            // base case: zero value
    for w := min to W do                 // bottom-up calculation of capacities
            K[w] := _{i : w_i ≤ w} { v_i + K[w - w_i] } // {#D9534F}{≤ftarrow O(n)} // DP recurrence equation
    return K[W]                          // optimal value for capacity W
```

(remember that $\textsf w$ is the remaining capacity, used as the loop iterator, while $w$, from which $w_i$ is read, is the array of weights of each item $i$)

📌 Note: if for a given capacity $w$ no item has $w_i \le w$, the maximum over an empty set is conventionally $0$.

📌 Note 2:
For the Knapsack problem with repetition, the algorithm only computes the maximum value $K[W]$, regardless of which combination (which may not be unique) of items constitutes it.
To compute $K[w]$ numerically, the algorithm does not need to know which items were used in previous steps: knowing the numerical value $K[w - w_i]$ is sufficient.
If necessary, one can still backtrack to reconstruct the items (without having to store additional data):
Start at $w=W$ and check which item i satisfies the equation:

$$

K[w] = v_i + K[w - w_i]

$$

Once item i is found:
**1.** Add it to the solution.
**2.** Move to the remaining capacity $w \leftarrow w - w_i$.
**3.** Repeat the check until reaching $w = 0$.

```text
Reconstruct_Solution(W, n, w, v, K)
    w := W                               // Initial remaining capacity = total capacity
    solution := [ ]                      // List of chosen items
    while w > 0 do
        for i := 1 to n do
            if w_i ≤ w and K[w] = v_i + K[w - w_i] then
                add i to solution
                w := w - w_i                         // Decrease remaining capacity
                break                                // Immediately proceed to next while iteration
    return solution
```

(remember that $\textsf w$ is the remaining capacity while $w$, from which $w_i$ is read, is the weight array)

**Alternatively**, during the computation phase, whenever the index $i$ maximizing the formula is found, store it in an **auxiliary array** $\textsf{choice}[w]$.

```text
Knapsack_With_Repetition_With_Trace(W, n, w, v)
    min := _{i ∈ [1..n]} { w_i }
    for w := 0 to min - 1 do
        K[w] := 0
        {#FF6600}{choice}[w] := 0
    for w := min to W do
        K[w] := 0
        {#FF6600}{choice}[w] := 0
        for i := 1 to n do
            if w_i ≤ w and (v_i + K[w - w_i] > K[w]) then
                K[w] := v_i + K[w - w_i]
                {#FF6600}{choice}[w] := i // Save the last item inserted for capacity w
    return K[W], {#FF6600}{choice}
```

Once the algorithm terminates, to reconstruct the list of items starting from $W$, run a simple loop backward (backtracking):

```text
Reconstruct_Solution(W, w, {#FF6600}{choice})
    w := W                               // Initial remaining capacity = total capacity
    solution := [ ]                      // List of chosen items
    while w > 0 and {#FF6600}{choice}[w] ≠q 0 do
        i := {#FF6600}{choice}[w]            // Retrieve the last item inserted
        add i to solution
        w := w - w_i                         // Decrease remaining capacity
    return solution
```
