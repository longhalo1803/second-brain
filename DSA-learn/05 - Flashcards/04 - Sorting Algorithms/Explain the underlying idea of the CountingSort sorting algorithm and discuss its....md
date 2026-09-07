---
title: "Explain the underlying idea of the CountingSort sorting algorithm and discuss its..."
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
  - "Explain the underlying idea of the CountingSort sorting algorithm and discuss its..."
---

# 🎴 Explain the underlying idea of the CountingSort sorting algorithm and discuss its...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: ❓ Explain the underlying idea of the CountingSort sorting algorithm and discuss its computational cost. #card

?

- **Basic Idea of CountingSort:**
  CountingSort is a **non-comparison-based** sorting algorithm. It assumes that the $n$ elements of the input array $A$ are integers within a known range $[0, k]$.
  The core idea consists of determining, for each element $x$, the number of elements strictly less than it. With this information, element $x$ can be placed directly and unambiguously into its exact final position within an output array $B$.
- Create a frequency array $C[0 \dots k]$ initialized to 0.
- Iterate through $A$ and count how many times each value appears: $C[A[i]]++$.
- Compute prefix sums in $C$ ($C[j] = C[j] + C[j-1]$), so that $C[x]$ stores the total number of elements less than or equal to $x$.
- Iterate through $A$ **backwards** (from $n-1$ down to $0$) and place each element into its proper position: $B[C[A[i]] - 1] = A[i]$, then decrement $C[A[i]]$. Scanning backwards guarantees the **stability** of the algorithm.
- **Computational Cost:**
- Initialization of $C$: $\mathcal{O}(k)$.
- Frequency counting: $\mathcal{O}(n)$.
- Prefix sums: $\mathcal{O}(k)$.
- Placement into output: $\mathcal{O}(n)$.
- **Total Time:** $\mathcal{O}(n + k)$. If the key range is linear with respect to the input size, i.e., $k = \mathcal{O}(n)$, the running time is strictly linear $\mathcal{O}(n)$, beating the $\Omega(n \log n)$ lower bound of comparison-based algorithms.
- **Auxiliary Space:** $\mathcal{O}(n + k)$ to hold the auxiliary array $C$ of size $k+1$ and the output array $B$ of size $n$.
