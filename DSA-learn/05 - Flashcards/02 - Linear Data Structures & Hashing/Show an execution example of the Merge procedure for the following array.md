---
title: "Show an execution example of the Merge procedure for the following array"
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
  - "Show an execution example of the Merge procedure for the following array"
---

# 🎴 Show an execution example of the Merge procedure for the following array

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: 📝 Show an execution example of the Merge procedure for the following array:

$$

\begin{array}{c l c c l}
\text{A} &
\overset{\ell}{{\vphantom{\mathbf{1}}\color{white}{\mathbf{1}}}}
\overset{\vphantom{\ell}}{{\vphantom{\mathbf{1}}\color{white}{\mathbf{3}}}}
\overset{\vphantom{\ell}}{{\vphantom{\mathbf{1}}\color{white}{\mathbf{7}}}}
\overset{\vphantom{\ell}}{{\vphantom{\mathbf{1}}\color{white}{\mathbf{9}}}}
\overset{r}{{\vphantom{\mathbf{1}}\color{white}{\mathbf{2}}}}
\overset{\vphantom{\ell}}{{\vphantom{\mathbf{1}}\color{white}{\mathbf{4}}}}
\overset{\vphantom{\ell}}{{\vphantom{\mathbf{1}}\color{white}{\mathbf{6}}}}
\overset{\vphantom{\ell}}{{\vphantom{\mathbf{1}}\color{white}{\mathbf{8}}}}
& \qquad &
\text{B} &
\overset{t}{{\vphantom{\mathbf{1}}\phantom{\mathbf{1}}}}
\overset{\vphantom{t}}{{\vphantom{\mathbf{1}}\phantom{\mathbf{1}}}}
\overset{\vphantom{t}}{{\vphantom{\mathbf{1}}\phantom{\mathbf{1}}}}
\overset{\vphantom{t}}{{\vphantom{\mathbf{1}}\phantom{\mathbf{1}}}}
\overset{\vphantom{t}}{{\vphantom{\mathbf{1}}\phantom{\mathbf{1}}}}
\overset{\vphantom{t}}{{\vphantom{\mathbf{1}}\phantom{\mathbf{1}}}}
\overset{\vphantom{t}}{{\vphantom{\mathbf{1}}\phantom{\mathbf{1}}}}
\overset{\vphantom{t}}{{\vphantom{\mathbf{1}}\phantom{\mathbf{1}}}}
\end{array}

$$

#card
?

```text
A                                    // {}{[background: #a46bcf; border: 1px solid #555; padding: 10px 12px;]{{{1}}{white}{{1}}}} -1px {{}}{[background: #a46bcf; border: 1px solid #555; padding: 10px 12px;]{{{1}}{white}{{3}}}} -1px {{}}{[background: #a46bcf; border: 1px solid #555; padding: 10px 12px;]{{{1}}{white}{{7}}}} -1px {{}}{[background: #a46bcf; border: 1px solid #555; padding: 10px 12px;]{{{1}}{white}{{9}}}} -1px {r}{[background: #42bda9; border: 1px solid #555; padding: 10px 12px;]{{{1}}{white}{{2}}}} -1px {{}}{[background: #42bda9; border: 1px solid #555; padding: 10px 12px;]{{{1}}{white}{{4}}}} -1px {{}}{[background: #42bda9; border: 1px solid #555; padding: 10px 12px;]{{{1}}{white}{{6}}}} -1px {{}}{[background: #42bda9; border: 1px solid #555; padding: 10px 12px;]{{{1}}{white}{{8}}}}
        [1em]                                // 120px
[1em] A                              // {{}}{[background: #a46bcf; border: 1px solid #555; padding: 10px 12px;]{{{1}}{{1}}}} -1px {{}}{[background: #a46bcf; border: 1px solid #555; padding: 10px 12px;]{{{1}}{{1}}}} -1px {{}}{[background: #a46bcf; border: 1px solid #555; padding: 10px 12px;]{{{1}}{{1}}}} -1px {}{[background: #a46bcf; border: 1px solid #555; padding: 10px 12px;]{{{1}}{white}{{9}}}} -1px {{}}{[background: #42bda9; border: 1px solid #555; padding: 10px 12px;]{{{1}}{{1}}}} -1px {{}}{[background: #42bda9; border: 1px solid #555; padding: 10px 12px;]{{{1}}{{1}}}} -1px {{}}{[background: #42bda9; border: 1px solid #555; padding: 10px 12px;]{{{1}}{{1}}}} -1px {r}{[background: #42bda9; border: 1px solid #555; padding: 10px 12px;]{{{1}}{white}{{8}}}}
[1em] A                              // {{}}{[background: #a46bcf; border: 1px solid #555; padding: 10px 12px;]{{{1}}{{1}}}} -1px {{}}{[background: #a46bcf; border: 1px solid #555; padding: 10px 12px;]{{{1}}{{1}}}} -1px {{}}{[background: #a46bcf; border: 1px solid #555; padding: 10px 12px;]{{{1}}{{1}}}} -1px {}{[background: #a46bcf; border: 1px solid #555; padding: 10px 12px;]{{{1}}{white}{{9}}}} -1px {{}}{[background: #42bda9; border: 1px solid #555; padding: 10px 12px;]{{{1}}{{1}}}} -1px {{}}{[background: #42bda9; border: 1px solid #555; padding: 10px 12px;]{{{1}}{{1}}}} -1px {{}}{[background: #42bda9; border: 1px solid #555; padding: 10px 12px;]{{{1}}{{1}}}} -1px {{}}{[background: #42bda9; border: 1px solid #555; padding: 10px 12px;]{{{1}}{{1}}}} 12px { 1.4em{$r$}}
[1em] A                              // {{}}{[background: #a46bcf; border: 1px solid #555; padding: 10px 12px;]{{{1}}{{1}}}} -1px {{}}{[background: #a46bcf; border: 1px solid #555; padding: 10px 12px;]{{{1}}{{1}}}} -1px {{}}{[background: #a46bcf; border: 1px solid #555; padding: 10px 12px;]{{{1}}{{1}}}} -1px {, h}{[background: #a46bcf; border: 1px solid #555; padding: 10px 12px;]{{{1}}{{1}}}} -1px {{}}{[background: #42bda9; border: 1px solid #555; padding: 10px 12px;]{{{1}}{{1}}}} -1px {{}}{[background: #42bda9; border: 1px solid #555; padding: 10px 12px;]{{{1}}{{1}}}} -1px {{}}{[background: #42bda9; border: 1px solid #555; padding: 10px 12px;]{{{1}}{{1}}}} -1px {{}}{[background: #42bda9; border: 1px solid #555; padding: 10px 12px;]{{{1}}{white}{{9}}}} 12px { 1.4em{$r$}}
[1em] A                              // {{}}{[background: #a46bcf; border: 1px solid #555; padding: 10px 12px;]{{{1}}{white}{{1}}}} -1px {{}}{[background: #a46bcf; border: 1px solid #555; padding: 10px 12px;]{{{1}}{white}{{2}}}} -1px {{}}{[background: #a46bcf; border: 1px solid #555; padding: 10px 12px;]{{{1}}{white}{{3}}}} -1px {, h}{[background: #a46bcf; border: 1px solid #555; padding: 10px 12px;]{{{1}}{white}{{4}}}} -1px {{}}{[background: #42bda9; border: 1px solid #555; padding: 10px 12px;]{{{1}}{white}{{6}}}} -1px {{}}{[background: #42bda9; border: 1px solid #555; padding: 10px 12px;]{{{1}}{white}{{7}}}} -1px {{}}{[background: #42bda9; border: 1px solid #555; padding: 10px 12px;]{{{1}}{white}{{8}}}} -1px {{}}{[background: #42bda9; border: 1px solid #555; padding: 10px 12px;]{{{1}}{white}{{9}}}} 12px { 1.4em{$r$}}
```

Merge Pseudocode$\begin{array}{ll}
\textsf{Merge(A, i, k, j)} & \\
\quad \texttt{l} \textsf{ := i} & \small\textsf{// Index initialization} \\
\quad \texttt{r} \textsf{ := k + 1} & \\
\quad \texttt{t} \textsf{ := 0} & \\
\quad \textsf{B[0}..\textsf{j-i] new array} & \\
\quad \texttt{while } (\texttt{l} \le \textsf{k} \texttt{ AND } \texttt{r} \le \textsf{j}) \texttt{ do} & \small\textsf{// Comparisons and filling B} \\
\quad\quad \texttt{if } \textsf{A[}\texttt{l}\textsf{]} \le \textsf{A[}\texttt{r}\textsf{]} \texttt{ then} & \\
\quad\quad\quad \textsf{B[}\texttt{t}\textsf{] := A[}\texttt{l}\textsf{]} & \\
\quad\quad\quad \texttt{l} \textsf{ := } \texttt{l} \textsf{ + 1} & \\
\quad\quad \texttt{else} & \\
\quad\quad\quad \textsf{B[}\texttt{t}\textsf{] := A[}\texttt{r}\textsf{]} & \\
\quad\quad\quad \texttt{r} \textsf{ := } \texttt{r} \textsf{ + 1} & \\
\quad\quad \texttt{t} \textsf{ := } \texttt{t} \textsf{ + 1} & \\
\quad \texttt{for } \textsf{h := k} \texttt{ downto } \texttt{l} \texttt{ do} & \small\textsf{// Copy remaining left elements to the end} \\
\quad\quad \textsf{A[j] := A[h]} & \\
\quad\quad \textsf{j := j - 1} & \\
\quad \texttt{for } \textsf{h := 0} \texttt{ to } \texttt{t} \textsf{ - 1} \texttt{ do} & \small\textsf{// Copy B back into A} \\
\quad\quad \textsf{A[i + h] := B[h]} &
\end{array}$
