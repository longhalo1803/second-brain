---
title: "5 Given a list L storing natural numbers, write a procedure that modifies list L i..."
tags:
  - dsa
  - flashcards
  - clrs
  - graphs
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "5 Given a list L storing natural numbers, write a procedure that modifies list L i..."
---

# 🎴 5 Given a list L storing natural numbers, write a procedure that modifies list L i...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 📝 5 Given a list $L$ storing natural numbers, write a procedure that **modifies** list $L$ in-place so that it contains **only odd numbers** (using the $\textsf{delete}$ primitive). Provide both the iterative and recursive versions and analyze their complexity.

⚠️ The exercise differs from Exercise 4 because, in this case, you are asked to modify the input list.
📌 Note: for simplicity, we will always assume that the function delete(L, p) merely disconnects node $p$ from list $L$ (by updating the pointers of adjacent nodes) without deallocating the memory occupied by $p$, so node $p$ still exists in memory and can be reused. #card
?
**1. Iterative Solution:**

```text
{aligned}                            // OddListI(L)
        // if L ≠q NIL then {gray}// (redundant)
        // p := L
        // while p ≠q NIL do
            // if (p.val 2 = 0) then
                // delete(L, p)
            // p := p.next {aligned}
```

(an auxiliary pointer $\textsf p$ is needed, otherwise the reference to the original list $\textsf L$ would be lost!)
**
\*\***2. Recursive Solution:\*\*

- **Base case:** Empty list ($\textsf{p} = \textsf{NIL}$), no action.
- **Recursive case:** If $\textsf{p.val}$ is even, delete node $\textsf{p}$ using $\textsf{delete}(\textsf{L}, \textsf{p})$; then proceed recursively on $\textsf{p.next}$.

```text
{aligned}                            // OddListR(L, p)
    // if p ≠q NIL then
        // if (p.val 2 = 0) then
            // delete(L, p)
        // OddListR(L, p.next) {aligned}
```

**Main call:** $\texttt{OddListR}(\textsf{L}, \textsf{L})$

⚠️ **Caution regarding computational complexity:**
The primitive $\textsf{delete}(\textsf{L}, \textsf{p})$ scans the list starting from the head $\textsf{L}$ until it finds the node preceding $\textsf{p}$.
In the _worst case_ (for example, a list where the first half of the nodes contains odd numbers and the second half contains only even numbers), each call to $\textsf{delete}$ takes time proportional to the position of $\textsf{p}$, resulting in an overall computational cost of $\Theta(n^2)$.

📌 Note:
If instead we assumed that values were deallocated, the following changes would be necessary (namely, do not delete `p` and then attempt to access it with `p.next` immediately after when it has already been deallocated):
$\begin{aligned}
&\texttt{OddListI}(\textsf{L}) \\
&\quad \textsf{p} := \textsf{L} \\
&\quad \texttt{while } \textsf{p} \neq \textsf{NIL} \texttt{ do} \\
&\quad\quad \textsf{succ} := \textsf{p.next} \quad \small\color{gray}\text{// save next node before deleting} \\
&\quad\quad \texttt{if } (\textsf{p.val} \bmod 2 = 0) \texttt{ then} \\
&\quad\quad\quad \texttt{delete}(\textsf{L}, \textsf{p}) \\
&\quad\quad \textsf{p} := \textsf{succ}
\end{aligned}$

$\begin{aligned} &\texttt{OddListR}(\textsf{L}, \textsf{p}) \\ &\quad \texttt{if } \textsf{p} \neq \textsf{NIL} \texttt{ then} \\ &\quad\quad \textsf{succ} := \textsf{p.next} \quad \small\color{gray}\text{// save next node before deleting} \\ &\quad\quad \texttt{if } (\textsf{p.val} \bmod 2 = 0) \texttt{ then} \\ &\quad\quad\quad \texttt{delete}(\textsf{L}, \textsf{p}) \\ &\quad\quad \texttt{OddListR}(\textsf{L}, \textsf{succ}) \end{aligned}$
