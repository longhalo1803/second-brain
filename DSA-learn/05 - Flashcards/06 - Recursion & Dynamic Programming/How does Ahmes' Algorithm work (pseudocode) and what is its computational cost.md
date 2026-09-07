---
title: "How does Ahmes' Algorithm work (pseudocode) and what is its computational cost"
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
  - "How does Ahmes' Algorithm work (pseudocode) and what is its computational cost"
---

# 🎴 How does Ahmes' Algorithm work (pseudocode) and what is its computational cost

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: How does **Ahmes' Algorithm** work (pseudocode) and what is its **computational cost**? #card

?
Ahmes' Algorithm is a recursive algorithm (which does not use column multiplication and originates from an ancient papyrus dated ~1500 BC, although not in the recursive form below) to compute the multiplication of two non-negative integers $a$ and $b$.

**INPUT**: two non-negative integers, a and b
**OUTPUT**: the product a\*b
Pseudocode:

```text
Ahmes(a, b)
    if a = 0 then return 0               // base cases
    if a = 1 then return b
    if a mod 2 = 0                       // a is even
        then return Ahmes(a / 2, 2b)
    else return Ahmes((a - 1) / 2, 2b) + b // a is odd
```

The algorithm leverages algebraic properties:
If $a$ is even $\implies a \cdot b = (a/2) \cdot (2b)$
If $a$ is odd $\implies a \cdot b = \frac{a-1}{2} \cdot (2b) + b$

Let's verify that it works, proceeding by cases:
_Recursive case a = 0_: If a = 0, then a*b = 0 (regardless of the value of b) and Ahmes(0,b) = 0 ✅
*Recursive case a = 1*: If a = 1, then a*b = b (regardless of the value of b) and Ahmes(1,b) = b ✅
_Recursive case: a > 1_:
**Subcase 1**: a > 1 and even; to compute the product of a and b, Ahmes computes the product of a/2 and 2b:
a*b = (a/2)*(2b) and a/2 is an integer and non-negative ✅
**Subcase 2**: a > 1 and odd;
to compute the product of a and b, Ahmes computes the product
of (a-1)/2 and 2b and subsequently adds b to the result:
(a-1)/2*b +b = (a/2)*(2b) - b + b = a\*b
and (a-1)/2 is an integer and non-negative ✅
There are no other cases, so we are certain that the algorithm works.

**Computational cost:**
The number of logical-arithmetic operations to execute at each recursive call is constant, but how many recursive calls?
The recursion halves parameter $a$ at each step.
The number of recursive calls to reach the base case $a=1$ is therefore the number of times it is possible to divide $a$ by 2, which equals $\lfloor \log_2 a \rfloor$.
Proof:
Let k be such that $2^{k+1} < n \leq 2^k \implies k = \lfloor \log n \rfloor$
$\implies$ $n$ can be represented with $k + 1$ bits
$\implies$ after $i$ iterations the remaining portion has at most $\lfloor n/2^i \rfloor$ elements
which is equivalent to a right shift of the binary representation of $n$ by $i$ positions
$\implies$ to be left with one binary digit (i.e. $a=1$), $k$ shifts (i.e. calls) are necessary

Since the work done at each individual call is bounded by basic logical-arithmetic operations ($O(1)$), the total time is $\Theta(\log a)$.

📌 Note:
A logarithmic cost with respect to the value of $a$ means that the algorithm actually has a linear time complexity relative to the number of bits required to represent the memory size of $a$.
