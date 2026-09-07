---
title: "What does the array look like at the beginning, during, and at the end of the gene..."
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
  - "What does the array look like at the beginning, during, and at the end of the gene..."
---

# 🎴 What does the array look like at the beginning, during, and at the end of the gene...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What does the array look like at the beginning, during, and at the end of the generic iteration _j_ of InsertionSort? #card

?
****InsertionSort — Generic Iteration $j$****

**1. At the beginning of iteration $j$:**

$$
\underbrace{
\overset{\text{0}}{{\vphantom{\text{unsorted}}\dots}}
{\vphantom{\text{unsorted}}\text{sorted}}
\overset{\text{j-1}}{{\vphantom{\text{unsorted}}\dots}}
}_{\small\text{j elements (cards in hand)}}
\underbrace{
\overset{\text{j}}{{\vphantom{\text{unsorted}}\dots}}
{\vphantom{\text{unsorted}}\text{unsorted}}
\overset{\text{n-1}}{{\vphantom{\text{unsorted}}\dots}}
}_{\small\text{n - j elements (not in hand)}}
$$

**2. Backward insertion of $A[j]$:**

We take element $A[j]$ and compare it to the left:

- If $A[j-1] > A[j]$, we swap and continue comparing to the left:

$$
\begin{array}{c}
\overset{\text{0}}{{\vphantom{\text{unsorted}}\dots}}
{\vphantom{\text{unsorted}}\text{sorted}}
\overset{\large\color{#E65100}{\curvearrowleft}}{
\overset{\text{j-1}}{{\vphantom{\text{unsorted}}\dots}}
\overset{\text{j}}{{\vphantom{\text{unsorted}}\dots}}
}
{\vphantom{\text{unsorted}}\text{unsorted}}
\overset{\text{n-1}}{{\vphantom{\text{unsorted}}\dots}}
\end{array}
$$

$$
\overset{\text{0}}{{\vphantom{\text{unsorted}}\dots}}
{\vphantom{\text{unsorted}}\text{sorted}}
\overset{\text{j-1}}{{\vphantom{\text{unsorted}}\dots}}
\overset{\text{j}}{{\vphantom{\text{unsorted}}\dots}}
{\vphantom{\text{unsorted}}\text{unsorted}}
\overset{\text{n-1}}{{\vphantom{\text{unsorted}}\dots}}
$$

**We stop when:**

- We find $A[i-1] \le A[i]$ (the element is in its correct position).
- Or the first position is reached ($i = 0$):

$$
\overset{\text{i = 0}}{{\vphantom{\text{unsorted}}A[j]}}
{\vphantom{\text{unsorted}}\text{sorted}}
\overset{\text{j}}{{\vphantom{\text{unsorted}}\dots}}
{\vphantom{\text{unsorted}}\text{unsorted}}
\overset{\text{n-1}}{{\vphantom{\text{unsorted}}\dots}}
$$

**📌 **Note:
$j$ (outer loop) selects the new element (fixed at each iteration) to insert and moves forward (from left to right: $1, 2, 3 \dots$).
$i$ (inner loop) moves the element _to the left_ by comparing it backward until it finds its correct position.

**3. At the end of iteration **$j$**:**

$$
\underbrace{
\overset{\text{0}}{{\vphantom{\text{unsorted}}\dots}}
{\vphantom{\text{unsorted}}\text{sorted}}
\overset{\text{j-1}}{{\vphantom{\text{unsorted}}\dots}}
\overset{\text{j}}{{\vphantom{\text{unsorted}}\dots}}
}_{\text{j + 1 elements}}
\underbrace{
\overset{\text{j+1}}{{\vphantom{\text{unsorted}}\dots}}
{\vphantom{\text{unsorted}}\text{unsorted}}
\overset{\text{n-1}}{{\vphantom{\text{unsorted}}\dots}}
}_{\text{n - j - 1 elements}}
$$

**4. Edge cases:**

- **Before starting ($j=1$):** $A[0]$ forms a sorted subsequence of 1 element by itself.
- **At the end ($j=n$):** The entire array of $n$ elements is fully sorted.

  `g40`.elementShape

  `g40`.elementBacking

  `g40`.elementContent

  `g42`.elementShape

  `g42`.elementBacking

  `g41`.elementShape

  `g41`.elementBacking

  `r5`.pointedLine

  `g41`.elementContent

  `g8`.elementShape

  `g8`.elementBacking

  `g8`.elementContent

  `g10`.elementShape

  `g10`.elementBacking

  `g9`.elementShape

  `g9`.elementBacking

  `r2`.pointedLine

  `g10`.elementContent

  `g9`.elementContent

  `g21`.elementShape

  `g21`.elementBacking

  `g21`.elementContent

  `g13`.elementShape

  `g13`.elementBacking

  `g13`.elementContent

  `g4`.elementShape

  `g4`.elementBacking

  `g4`.elementContent

  `a2`.rect

  `a2`.arrayLabel

  `g30`.elementShape

  `g30`.elementBacking

  `g30`.elementContent

  `a3`.rect

  `a3`.arrayLabel

  `g6`.elementShape

  `g6`.elementBacking

  `g6`.elementContent

  `g7`.elementShape

  `g7`.elementBacking

  `g7`.elementContent

  `g3`.elementShape

  `g3`.elementBacking

  `g3`.elementContent

  `g34`.elementShape

  `g34`.elementBacking

  `g32`.elementShape

  `g32`.elementBacking

  `r4`.pointedLine

  `g34`.elementContent

  `g32`.elementContent

  `g2`.elementShape

  `g2`.elementBacking

  `g1`.elementShape

  `g1`.elementBacking

  `r1`.pointedLine

  `g2`.elementContent

  `g1`.elementContent

  `a1`.rect

  `a1`.arrayLabel

  `g17`.elementShape

  `g17`.elementBacking

  `g17`.elementContent

  `g45`.elementShape

  `g45`.elementBacking

  `g45`.elementContent

  `g46`.elementShape

  `g46`.elementBacking

  `g46`.elementContent

  `g44`.elementShape

  `g44`.elementBacking

  `g44`.elementContent

  `a5`.rect

  `a5`.arrayLabel

  `g27`.elementShape

  `g27`.elementBacking

  `g27`.elementContent

  `g16`.elementShape

  `g16`.elementBacking

  `g16`.elementContent

  `g5`.elementShape

  `g5`.elementBacking

  `g5`.elementContent

  `g47`.elementShape

  `g47`.elementBacking

  `g47`.elementContent

  `g43`.elementShape

  `g43`.elementBacking

  `g43`.elementContent

  `g24`.elementShape

  `g24`.elementBacking

  `g24`.elementContent

  `g42`.elementContent

  `g35`.elementShape

  `g35`.elementBacking

  `g35`.elementContent

  `g26`.elementShape

  `g26`.elementBacking

  `g22`.elementShape

  `g22`.elementBacking

  `r3`.pointedLine

  `g22`.elementContent

  `g48`.elementShape

  `g48`.elementBacking

  `g48`.elementContent

  `g38`.elementShape

  `g38`.elementBacking

  `g38`.elementContent

  `g29`.elementShape

  `g29`.elementBacking

  `g29`.elementContent

  `g19`.elementShape

  `g19`.elementBacking

  `g19`.elementContent

  `g31`.elementShape

  `g31`.elementBacking

  `g31`.elementContent

  `g39`.elementShape

  `g39`.elementBacking

  `g39`.elementContent

  `g23`.elementShape

  `g23`.elementBacking

  `g23`.elementContent

  `g18`.elementShape

  `g18`.elementBacking

  `g18`.elementContent

  `g26`.elementContent

  `g37`.elementShape

  `g37`.elementBacking

  `g37`.elementContent

  `g11`.elementShape

  `g11`.elementBacking

  `g11`.elementContent

  `g28`.elementShape

  `g28`.elementBacking

  `g28`.elementContent

  `g12`.elementShape

  `g12`.elementBacking

  `g12`.elementContent

  `g49`.elementShape

  `g49`.elementBacking

  `g49`.elementContent

  `a6`.rect

  `a6`.arrayLabel

  `g33`.elementShape

  `g33`.elementBacking

  `g33`.elementContent

  `g14`.elementShape

  `g14`.elementBacking

  `g14`.elementContent

  `a4`.rect

  `a4`.arrayLabel

  `g20`.elementShape

  `g20`.elementBacking

  `g20`.elementContent

  `g25`.elementShape

  `g25`.elementBacking

  `g25`.elementContent

  `g36`.elementShape

  `g36`.elementBacking

  `g36`.elementContent

  `a7`.rect

  `a7`.arrayLabel

  `p1`.rect

  `p2`.rect

  `p3`.rect

  `p4`.rect

  `p5`.rect

  `p6`.rect
