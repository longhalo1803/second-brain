---
title: "Why does SelectionSort work Explain the correctness invariantproof of why it alway..."
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
  - "Why does SelectionSort work Explain the correctness invariantproof of why it alway..."
---

# 🎴 Why does SelectionSort work Explain the correctness invariantproof of why it alway...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: Why does SelectionSort work? Explain the correctness invariant/proof of why it always works, step by step #card

?
**Property / invariant (\*):**

Before the generic call on $A[i \dots n-1]$, the first $i$ elements are already sorted, and the following property holds:

```text
A[z] ≤ A[t] z ∈ [0 i-1], \, t ∈ [i n-1] (*)
```

$$
\underbrace{
\overset{\text{0}\;\;\;\;\;\;\;}{{\vphantom{\text{unsorted}}\dots}}
{\vphantom{\text{unsorted}}\text{sorted}}
\overset{\text{}}{{\vphantom{\text{unsorted}}\dots}}
}_{\text{i elements}}
\underbrace{
\overset{\text{i}}{{\vphantom{\text{unsorted}}\dots}}
{\vphantom{\text{unsorted}}\text{unsorted}}
\overset{\;\;\;\;\;\text{n-1}}{{\vphantom{\text{unsorted}}\dots}}
}_{\text{n - i elements}}
$$

**During the call:**

The minimum of the range $A[i \dots n-1]$ (at index $k$) is found and swapped with the element at position $i$:

$$
\underbrace{
\overset{\text{0}\;\;\;\;\;\;\;}{{\vphantom{\text{unsort.}}\dots}}
{\vphantom{\text{unsort.}}\text{sorted}}
\overset{\text{}}{{\vphantom{\text{unsort.}}\dots}}
}_{\text{i elements}}
\underbrace{
\overset{\text{i}}{{\vphantom{\text{unsort.}}A[i]}}
{\vphantom{\text{unsort.}}\text{unsort.}}
\overset{\text{k}}{{\vphantom{\text{unsort.}}\text{min}}}
\overset{\;\;\;\;\;\text{n-1}}{{\vphantom{\text{unsort.}}\dots}}
}_{\text{n - i elements}}
$$

**Why does the invariant still hold before the call on $A[i+1 \dots n-1]$?**

**1) Are the first $i+1$ elements $A[0 \dots i]$ sorted? YES**

- Nothing changed up to index $i-1$.
- $A[i]$ is $\ge$ all values in $A[0 \dots i-1]$ due to property (\*).

$$
\underbrace{
\overset{\text{0}\;\;\;\;\;\;}{{\vphantom{\text{unsorted}}\small\dots}}
{\vphantom{\text{unsorted}}\text{sorted}}
\overset{\text{}}{{\vphantom{\text{unsorted}}\small\dots}}
\overset{\text{i}}{{\vphantom{\text{unsorted}}\small\dots}}
}_{\text{i + 1 elements}}
\underbrace{
\overset{\text{i+1}}{{\vphantom{\text{unsorted}}\small\dots}}
{\vphantom{\text{unsorted}}\text{unsorted}}
\overset{\;\;\;\;\text{n-1}}{{\vphantom{\text{unsorted}}\small\dots}}
}_{\text{n - i - 1 elements}}
$$

**2) Does property (\*) still hold? That is, is it true that $A[z] \le A[t] \quad \forall z \in [0 \dots i], \, t \in [i+1 \dots n-1]$? YES**

- Nothing changed for the index ranges $[0 \dots i-1]$ and $[i+1 \dots n-1]$.
- In $A[i]$, we placed the minimum of $A[i \dots n-1]$, so it is true that $A[i] \le A[t] \quad \forall t \in [i+1 \dots n-1]$.

**Edge cases:**

- **Before the first call ($i=0$):** the sorted portion has size zero.

$$
\underbrace{
\overset{\text{i = 0}}{{\vphantom{\text{unsorted}}\;\;\,}}
{\vphantom{\text{unsorted}}\text{unsorted}}
\overset{\text{n-1}}{{\vphantom{\text{unsorted}}\;\;\,}}
}_{\text{n elements}}
$$

- **Before the last call ($i=n-1$):** there is only one "unsorted" element. By property (\*), $A[n-1]$ is already the maximum of the entire array and is in the correct position.

$$
\underbrace{
\overset{\text{0}}{{\vphantom{\text{sorted}}\;\;\;\;\;\,}}
{\vphantom{\text{sorted}}\text{sorted}}
}_{\text{n - 1 elements}}
\underbrace{
\overset{\text{i = n-1}}{{\vphantom{\text{sorted}}\phantom{\dots}}}
}_{\small\substack{\text{1 elem.}\\\text{"unsorted"}}}
$$
