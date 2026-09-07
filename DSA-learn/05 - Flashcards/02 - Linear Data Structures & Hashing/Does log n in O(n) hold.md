---
title: "Does log n in O(n) hold"
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
  - "Does log n in O(n) hold"
---

# 🎴 Does log n in O(n) hold

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: Does $\log n \in O(n)$ hold? #card

?
Yes.
A logarithmic function, past a certain point, never exceeds a linear function.

📌 Note: in computer science, $\log$ almost always means base 2: $\log_2$ (the relationship holds for any valid logarithm base, i.e., $>1$).

**Proof **by induction:
We need to show that there exist two constants $c>0$ and $n_0 \in \mathbb N$ such that for every $n \geq n_0$ it holds that

$$
\log n \leq cn
$$

with $c = 1$ and $n_0 = 1$ $\rightarrow \log n \leq n \quad \forall n \geq 1$.

- Base case: $n=1 \Rightarrow \log 1 = 0 \leq 1$.
- Hypothesis: $\log n \leq n$.
- Statement to prove: $\log(n + 1) \leq (n + 1)$.
- Inductive step:

```text
{align} (n+1)                        // ≤q (n+n)
// ≤q (2n)
// = _2 2 + n
// \ \ \ \ \ \ \ \ \ \ \ \ \ \ \
    // ≤q 1 \ \ \ \ + \ \ \ \ n (by inductive hypothesis: n ≤q n) {align}
```

($\log n$ on the right of $\leq$ was "upper-bounded" to become $n$, an operation allowed due to the initial hypothesis, to match the expression on the left side of the statement to prove)
Therefore $\log(n+1) \leq n+1$. Thus $\log n \in O(n)$.

📌 Other notable results on orders of magnitude:

- $\, n^k \in O(2^n)$ for every $k$.
- $\, n^x \in O(a^n)$ for $a > 1$.
- $\, 2^n \in O(n!)$.
- $\, n! \in O(n^n)$.
