---
title: "In terms of recursion, what are the base cases and recursive cases of recursive bi..."
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
  - "In terms of recursion, what are the base cases and recursive cases of recursive bi..."
---

# 🎴 In terms of recursion, what are the base cases and recursive cases of recursive bi...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: In terms of recursion, what are the **base cases** and **recursive cases** of recursive binary search?

$\begin{array}{ll}
\textsf{BinarySearch(L, i, j, key)} & \\
\quad \texttt{if } \textsf{j - i} < \texttt{0} \texttt{ then} & \\
\quad\quad \texttt{return } \texttt{-1} & \\
\quad \texttt{else} & \\
\quad\quad \textsf{k := } \lfloor(\textsf{i} + \textsf{j})/\texttt{2}\rfloor & \\
\quad\quad \texttt{if } \textsf{key} = \textsf{L[k]} \texttt{ then} & \\
\quad\quad\quad \texttt{return } \textsf{k} & \\
\quad\quad \texttt{if } \textsf{key} < \textsf{L[k]} \texttt{ then} & \\
\quad\quad\quad \texttt{return } \textsf{BinarySearch(L, i, k}\texttt{-}\textsf{1, key)} & \\
\quad\quad \texttt{else} & \\
\quad\quad\quad \texttt{return } \textsf{BinarySearch(L, k}\texttt{+}\textsf{1, j, key)} &
\end{array}$ #card
?
The structure features:

1. **Base cases (direct return of the result):**

- _Failure:_ If $j - i L[k]$, it returns the result of $\textsf{BinarySearch(L, k+1, j, key)}$.

```text
BinarySearch(L, i, j, key)
    if j - i < 0 then
        {#C0392B}{return -1}
    else
        k := floor((i + j) / 2)
        if key = L[k] then
            {#C0392B}{return k}
        if key < L[k] then
            {#C0392B}{return BinarySearch(L, i, k-1, key)}
        else
            {#C0392B}{return BinarySearch(L, k+1, j, key)}
```

📌 Note: all possible execution flows are guaranteed to terminate by encountering a $\texttt{return}$ instruction.
