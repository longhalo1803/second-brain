---
title: "2⃣ Consider the following problem (2)"
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
  - "2⃣ Consider the following problem (2)"
---

# 🎴 2⃣ Consider the following problem (2)

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📝📍2️⃣ Consider the following problem:

- **Input: **A sorted array $A$ storing $n$ integer values (both positive and negative) all distinct.
- **Output: **Print of all index pairs $(i, j)$ such that $0 \le i, j \le n - 1$, with $i \neq j$, for which $A[i] = 3 \cdot A[j]$ holds if they exist, the pair $(-1, -1)$ otherwise.
- Show an input and output example of the problem with array $A$ containing both positive and negative values.
- Provide a verbal explanation of an algorithm that solves the problem in sub-quadratic time in $n$.
- Provide the pseudocode of the algorithm described verbally above.
- Analyze the computational cost of the proposed algorithm. #card
  ?
  **1. Input and Output Example**

- **Input:** $A = \langle -9, -3, -1, 0, 2, 6, 12 \rangle$ with $n = 7$.

- **Output:**

- $(0, 1)$ since $A[0] = -9$ and $A[1] = -3 \implies -9 = 3 \cdot (-3)$

- $(1, 2)$ since $A[1] = -3$ and $A[2] = -1 \implies -3 = 3 \cdot (-1)$

- $(5, 4)$ since $A[5] = 6$ and $A[4] = 2 \implies 6 = 3 \cdot 2$

_(Example with no valid pairs: for $A = \langle -5, -2, 1, 4, 7 \rangle$, the output is the pair $(-1, -1)$)_.

**2. Explanation of the algorithm**

To solve the problem in **sub-quadratic time** ($O(n \log n)$ instead of $O(n^2)$), we exploit the fact that array $A$ is **sorted** and contains **all distinct** elements:

- We iterate through each element $A[i]$ of the array using an index $i$ from $0$ to $n - 1$.

- In order for an element $A[j]$ to exist such that $A[i] = 3 \cdot A[j]$, the value $A[i]$ must necessarily be **divisible by $3$** (i.e., $A[i] \bmod 3 = 0$).

- Furthermore, since all elements of the array are distinct, it is not possible to have $A[i] = A[j] = 0$ with $i \neq j$. Therefore, the value $0$ cannot form any valid pair and we can ignore it ($A[i] \neq 0$).

- If $A[i]$ is divisible by $3$ and non-zero, we calculate the target value $A[i] / 3$.

- Taking advantage of $A$'s sorted order, we search for the index $j$ of the target value using **binary search** (`BinarySearch`), which takes $O(\log n)$ time.

- If binary search finds the element at index $j$, we print the pair $(i, j)$ and set a boolean flag `found` to `true`.

- At the end of the main loop, if `found` remained `false`, we print the pair $(-1, -1)$.

**3. Pseudocode**

```text
PrintPairs(A, n)
    found := false
    for i := 0 to n - 1 do
        if A[i] 3 = 0 and A[i] ≠q 0 then
            target := A[i] / 3
            j := BinarySearch(A, 0, n - 1, target)
            if j ≠q -1 then
                print(i, j)
                found := true
    if not found then
        print(-1, -1)
```

Binary Search (helper function)$\begin{array}{ll} \textsf{BinarySearch(A, i, j, key)} & \\ \quad \texttt{if } j - i

**4. Analysis of computational cost**

- **Initialization:** Assigning the variable `found` takes $O(1)$ time.

- **Main loop:** Executed exactly $n$ times (with $i$ from $0$ to $n - 1$).

- The divisibility check $A[i] \bmod 3 = 0$ and division take constant time $O(1)$.

- In cases where $A[i]$ is divisible by $3$, a call to `BinarySearch` is made on an array of size $n$, taking $O(\log n)$ time.

- Print operations and flag updating take $O(1)$ time.

The total worst-case computational cost is expressed by the summation:

$$
T(n) = \sum_{i=0}^{n-1} \left( O(1) + O(\log n) \right) = n \cdot O(\log n) = O(n \log n)
$$

Since $O(n \log n)$ is strictly lower than quadratic complexity $O(n^2)$, the algorithm fully satisfies the requirement of the problem.
