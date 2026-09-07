---
title: "Exercise 4"
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
  - "Exercise 4"
---

# 🎴 Exercise 4

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📝 **Exercise 4**

Let $A=A[0]...A[n-1]$ be a sequence of $n$ integers sorted in non-decreasing order ($A[0]\le...\le A[n-1]$), which can be both positive and negative.
Design a recursive algorithm that counts the number of elements $> 0$ in $A$. Analyze the time computational cost of the proposed algorithm, justifying the claims made.

💡 **Hint**For the algorithm, given the middle index $k=\lfloor n/2\rfloor$, the number of values $> 0$ is equal to the sum of the values $> 0$ located in the subsequence $A[0]...A[k]$ and the values $>0$ located in the subsequence $A[k+1]...A[n-1]$.
For the computational cost, observe that, since the elements are sorted, at most one half (between the left and the right) can contain both negative and positive numbers. #card
?
Given a subsequence $A[i]\le...\le A[j]$, three cases can occur:
• **Base case 1:** if $A[i]>0$, then all other $j-i+1$ values in the sequence are also $> 0$.
• **Base case 2:** if $A[j]\le0$, then all other values in the sequence are also $\le0$ and none of them are greater than 0.
• **Non-base case:** if $A[i]\le0 \text{ and } A[j]>0$, then, given the middle index $k=\lfloor(j+i)/2\rfloor$, the number of values $> 0$ is equal to the recursive sum of the two subsequences.

```text
Algorithm(A, i, j)
    if A[i] > 0 then return j - i + 1
    if A[j] ≤ 0 then return 0
    k := floor( (j + i) / 2 )
    return Algorithm(A, i, k) + Algorithm(A, k+1, j)
```

The main call is $\textsf{Algorithm(A, 0, n-1)}$.

**Computational cost analysis:**
Since the elements are sorted, there exists a single index $t$ such that $A[z]\le0$ for every $z0$ for every $z\ge t$ (that is, $t$ is the first positive element). This index $t$ can reside in **only one** of the two halves to which recursion is applied. On the other half, the condition will immediately satisfy one of the two base cases, terminating in constant time $O(1)$. Consequently, there will be at most a single chain of deep recursive calls $O(\log n)$. At each level, a constant number of operations is executed. In total, the computational cost is $O(\log n)$.
