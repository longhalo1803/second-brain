---
title: "2⃣ Consider the following problem"
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
  - "2⃣ Consider the following problem"
---

# 🎴 2⃣ Consider the following problem

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📝📍2️⃣ Consider the following problem:

- **Input:** Sorted array $A$ of $n$ integers whose value can only be $0$ or $1$.
- **Output:** The number of occurrences of the number $1$ in $A$.Write the pseudocode of an algorithm based on the Divide&Conquer technique that requires $O(\log n)$ time in the worst case.Write the recurrence equation and solve it to show that the computational cost of the algorithm is indeed as required. #card
  ?
  **1. Description of the algorithm**
  Since the array is sorted and contains only $0$ and $1$, it has the structure $[0, 0, \dots, 0, 1, 1, \dots, 1]$.
  Extreme input cases (_edge-cases_) to test can be arrays of all 1s or all 0s, or single-element arrays.

We use the Divide&Conquer approach which proceeds by dividing the interval $[i, j]$ in half via $k = \lfloor(i + j)/2\rfloor$:
_Base case 1_: If $A[i] = 1$, then all elements from $i$ to $j$ are $1$. The number of $1$s in this interval is $j - i + 1$.
_Base case 2_: If $A[j] = 0$, there are no $1$s in the interval (returns $0$).
_Recursive step_:
If $A[k] = 1$, we know that all elements from $k$ to $j$ are $1$ (they are $j - k + 1$, both endpoints included). It only remains to recursively count the $1$s in the left half $[i, k-1]$.
If instead $A[k] = 0$, all elements from $i$ to $k$ are $0$, so we must recursively search only in the right half $[k+1, j]$.

The initial call will be `CountOnes(A, 0, n - 1)`.

**2. Pseudocode**

```text
CountOnes(A, i, j)
    if i > j then
        return 0
        {gray}{if A[i] = 1 then} \;{gray}{// Optional O(1) optimization}
        {gray}{return j - i + 1}
    {gray}{if A[j] = 0 then}
                    {gray}{return 0} \;\;{gray}{// Optional O(1) optimization}
    k := floor((i + j) / 2)
    if A[k] = 1 then
        return (j - k + 1) + CountOnes(A, i, k - 1)
    else
        return CountOnes(A, k + 1, j)
```

**3. Recurrence equation and resolution**
At each step of the algorithm:
Only one recursive call is executed on a subarray of size at most $\lfloor n/2 \rfloor$.
The work performed outside the recursive call (comparisons and index calculations) requires constant time $c = O(1)$.
The recurrence equation in the worst case is therefore:

$$
T(n) = \begin{cases} O(1) & \text{if } n \le 1 \\ T\left(\frac{n}{2}\right) + O(1) & \text{if } n > 1 \end{cases}
$$

**Resolution via Master Theorem:**
The equation is in the general form $T(n) = a T(n/b) + f(n)$ where:
$a = 1$
$b = 2$
$f(n) = O(1) = O(n^0)$
We calculate $n^{\log_b a} = n^{\log_2 1} = n^0 = 1$.
Since $f(n) = \Theta(n^{\log_b a}) = \Theta(1)$, we fall into Case 2 of the Master Theorem.
Therefore:

$$
T(n) = \Theta(n^{\log_b a} \log n) = \Theta(1 \cdot \log n) = O(\log n)
$$

This proves that the computational complexity in the worst case is indeed $O(\log n)$.
