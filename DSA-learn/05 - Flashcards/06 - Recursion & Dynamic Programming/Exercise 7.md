---
title: "Exercise 7"
tags:
  - dsa
  - flashcards
  - clrs
  - dynamic-programming
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "Exercise 7"
---

# 🎴 Exercise 7

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: 📝 **Exercise 7**

Consider the following problem: given a sequence $L$ of $n$ integers, print all elements of the sequence $L$ that are equal to the difference between the value of the immediately preceding element and that of the immediately following element (example: if $L=5,2,3,1,2$ then 2,1 is printed). Write a recursive procedure and an iterative one.

💡 **Hint**If $L$ has fewer than three elements, no value is printed. In general, however, the first value that could be printed is the second of the sequence (i.e. $L[1]$), the last is the second to last of the sequence (i.e. $L[n-2]$).
(a) iteratively, scanning the elements and checking the condition;
(b) recursively, observing that, once an element is checked, what remains is the same problem on a shorter sequence. #card
?
**Iterative Version:**

```text
Iterative_Differences(L)
    n := L.length
    if n ≥ 3 then
        prev := 0
        curr := 1
        succ := 2
        while succ ≤ n - 1 do
            if L[prev] - L[succ] = L[curr] then
                print L[curr]
            prev := prev + 1
            curr := curr + 1
            succ := succ + 1
```

**Recursive Version:**
Takes as input the sequence $L$, the index $i$ of the current value to verify, and $n$ total elements.
• **Base case:** for $n 0$, checks the property and executes the recursion on $i+1$.

```text
Recursive_Differences(L, i, n)
    if i ≤ n - 3 AND i > 0 then
        if L[i-1] - L[i+1] = L[i] then
            print L[i]
        Recursive_Differences(L, i+1, n)
```

Main call: $\textsf{Recursive_Differences(L, 1, L.length)}$. We start from $i=1$ because the first element has no predecessor.

**New exercise**: Show an instance of the problem with $n = 15$ and show the recursive calls and the return from the calls that are executed by the algorithm proposed as a solution.
