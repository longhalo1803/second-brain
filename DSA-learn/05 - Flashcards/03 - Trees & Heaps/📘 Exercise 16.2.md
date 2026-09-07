---
title: "📘 Exercise 16.2"
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
  - "📘 Exercise 16.2"
---

# 🎴 📘 Exercise 16.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 16.2

**Input:** An array $A$ of $n$ characters and a constant odd integer $k \in O(1)$ such that $k \le n$.
**Output:** TRUE if there exists a palindromic contiguous subsequence in $A$ of length at least $k$, FALSE otherwise.

Explain the algorithm in words, provide pseudocode, and analyze computational complexity. #card
?
**Reasoning:**
If a string contains a palindrome of length $L \ge k$, then by repeatedly trimming one character from both ends, it also contains a palindrome of length $k$ (since $k$ is odd and the center remains intact for odd lengths, or length $k-1$). Because $k \in O(1)$, we can simply check whether there is any palindrome of exact length $k$ centered at each possible index.

**Algorithm Description:**
Let $r = \lfloor k / 2 \rfloor$. For each center index $i$ from $r$ to $n - 1 - r$, test if the substring from $i - r$ to $i + r$ is a palindrome. Testing a substring of length $k$ takes at most $r = O(1)$ character comparisons. If any center matches, return TRUE. If no center matches, return FALSE.

**Pseudocode:**

```text
Algorithm HasPalindromeAtLeastK(A, n, k):
    r ≤ftarrow floor( k / 2 )
    for i ≤ftarrow r to n - 1 - r do
        is_pal ≤ftarrow true
        for d ≤ftarrow 1 to r do
            if A[i - d] ≠ A[i + d] then
                is_pal ≤ftarrow false
        if is_pal then return TRUE
    return FALSE
```

**Complexity:**
There are $n - 2r$ candidate centers. Each check takes $O(k) = O(1)$ steps since $k$ is a constant. Total time complexity is $O(n)$, with $O(1)$ auxiliary space.
