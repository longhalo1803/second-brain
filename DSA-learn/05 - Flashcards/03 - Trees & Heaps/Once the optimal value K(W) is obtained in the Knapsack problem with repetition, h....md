---
title: "Once the optimal value K(W) is obtained in the Knapsack problem with repetition, h..."
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
  - "Once the optimal value K(W) is obtained in the Knapsack problem with repetition, h..."
---

# 🎴 Once the optimal value K(W) is obtained in the Knapsack problem with repetition, h...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: Once the optimal value $K(W)$ is obtained in the Knapsack problem with repetition, how is the **reconstruction of the optimal selection** performed (_backtracking_)? #card

?
To trace back the chosen items and not just the optimal value $K(W)$:

- **Storing choices:** Maintain an auxiliary array $\text{choice}[0..W]$. While computing $K(w)$, store in $\text{choice}[w]$ the index of the item $i$ that achieved the maximum.
- **Backtracking:**

- Start from the total capacity $w = W$.
- While $w \ge \min_i \{ w_i \}$ and $\text{choice}[w] \ne 0$:
- Identify the inserted item: $i = \text{choice}[w]$.
- Add item $i$ to the solution.
- Decrease the remaining capacity: $w \leftarrow w - w_i$.

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

Once the algorithm terminates, to reconstruct the list of items starting from $W$, run a simple loop backward:

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

📝 Example:
If $W=10$, $\text{choice}[10] = 1$ (with $w_1=6$), the next step examines the remaining capacity $10 - 6 = 4$.
If $\text{choice}[4] = 4$ (with $w_4=2$), we proceed to $4 - 2 = 2$, where $\text{choice}[2] = 4$, terminating at capacity $0$. Final selection: 1 item 1 + 2 item 4.

📌 Note (alternative **without auxiliary array**):
Start from $w=W$ and check which item i satisfies the equation:

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

(remember that $\textsf w$ is the remaining capacity, used as the loop iterator, while $w$, from which $w_i$ is read, is the array of weights of each item $i$)
