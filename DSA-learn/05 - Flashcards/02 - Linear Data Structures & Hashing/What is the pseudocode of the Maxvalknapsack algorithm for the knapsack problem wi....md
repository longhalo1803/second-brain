---
title: "What is the pseudocode of the Maxvalknapsack algorithm for the knapsack problem wi..."
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
  - "What is the pseudocode of the Maxvalknapsack algorithm for the knapsack problem wi..."
---

# 🎴 What is the pseudocode of the Maxvalknapsack algorithm for the knapsack problem wi...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: 🟢 What is the pseudocode of the `Max_val_knapsack` algorithm for the knapsack problem without repetition? #card

?
The algorithm fills the subproblems matrix in a bottom-up manner:

```text
Max_val_knapsack(n, W, w_1..w_n, v_1..v_n)
    for w := 0 to W do
        K[0, w] := 0                         // initialize first row (w = 0)
    for i := 0 to n do
        K[i, 0] := 0                         // initialize first column (i = 0)
    for i := 1 to n do
        for w := 1 to W do
            if w_{i} > w then                    // if item i too large
                K[i, w] := K[i-1, w]                 // copy element from cell above
            else
                K[i, w] := max{K[i-1, w], v_{i} + K[i-1, w - w_{i}]\ }
    return K[n, W]                       // {orange}{≤ftarrow optimal solution}
```

(remember that $\textsf w$ is the remaining capacity, used as the loop iterator, while $w$, from which $w_i$ is read, is the array of weights of each item $i$)

⚠️ Warning:
The video shows the algorithm's implementation in Python, hence using 0-based indexing.
The pseudocode above is 1-based and would create an $(n+1) \times (W+1)$ matrix (rather than $n \times (W+1)$) like the following, where both row $i=0$ and column $w=0$ are filled with $0$ (since with no items or no capacity the obtained value is zero). This simplifies the code without needing to handle special cases, although it makes the full tabular representation slightly bulkier:

      i
      itm
      vi
      wi
      0
      1
      2
      3
      4
      5
      6
      7




      0
      –
      –
      –
      0
      0
      0
      0
      0
      0
      0
      0


      1
      A
      15
      1
      0
      15
      15
      15
      15
      15
      15
      15


      2
      B
      20
      3
      0
      15
      15
      20
      35
      35
      35
      35


      3
      C
      30
      4
      0
      15
      15
      20
      35
      45
      45
      50


      4
      D
      50
      5
      0
      15
      15
      20
      35
      50
      65
      65

Other videos:
The 0/1 Knapsack Problem (Demystifying Dynamic Programming) - Back To Back SWE
0/1 Knapsack Problem Explained Visually - ByteQuest
0/1 Knapsack problem | Dynamic Programming - WilliamFiset
Leggi anche:
Interactive visualizations:

📌 Note:
This algorithm fills the table by rows.
In the indexing $\textsf{K}[i, w]$, $i$ is the row (item from $0$ to $n$) and $w$ the column (capacity from $0$ to $W$): the outer loop fixes row $i$, while the inner loop iterates through all its columns $w$.
To fill the table by columns (computing for each capacity $w$ all items $i$ before incrementing the capacity), simply invert the order of the two `for` loops:
`for w := 1 to W do`
`for i := 1 to n do`

📌 Note 2:
So far, we have adopted the standard convention with items ($i$) on the rows and capacity ($w$) on the columns in the resulting matrix ($\textsf{K}[i, w]$), which is also better for performance thanks to the row-major order of modern programming languages (C, C++, Java, Python) since, when the inner loop iterates through $w$ from $1$ to $W$, memory accesses occur on contiguous cells ($\textsf{K}[i][1]$, $\textsf{K}[i][2]$, $\textsf{K}[i][3]$...).

To use the alternative convention, with capacity on the rows and items on the columns, i.e., the structure $\textsf{K}[w, j]$, the following minor changes will need to be made:

- _Swap the index positions_: each access $\textsf{K}[\text{row}, \text{column}]$ becomes $\textsf{K}[w, j]$. The previous column becomes $j-1$.
- _Update the initializations_:
- The first row ($w = 0$) sets all items $j$ to zero: $\textsf{K}[0, j] := 0$.
- The first column ($j = 0$) sets all weights $w$ to zero: $\textsf{K}[w, 0] := 0$.
- _Arrival point_: the optimal solution will be found in cell $\textsf{K}[W, n]$.
- _Column-by-column filling_: with this structure, keeping the outer loop over $j$ (from $1$ to $n$) and the inner loop over $w$ (from $1$ to $W$), the algorithm will compute the table by columns (item by item, iterating through all capacities).

```text
Max_val_knapsack(n, W, w_1..w_n, v_1..v_n)
    for j := 0 to n do
        K[0, j] := 0                         // initialize first row (w = 0)
    for w := 0 to W do
        K[w, 0] := 0                         // initialize first column (j = 0)
    for j := 1 to n do
        for w := 1 to W do
            if w_{j} > w then                    // if item j is too large
                K[w, j] := K[w, j-1]                 // copy the element from the cell to the left
            else
                K[w, j] := max{K[w, j-1], v_{j} + K[w - w_{j}, j-1]\ }
    return K[W, n]                       // {orange}{≤ftarrow optimal solution}
```
