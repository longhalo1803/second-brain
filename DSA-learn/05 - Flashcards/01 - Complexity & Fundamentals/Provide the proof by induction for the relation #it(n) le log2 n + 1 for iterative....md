---
title: "Provide the proof by induction for the relation #it(n) le log2 n + 1 for iterative..."
tags:
  - dsa
  - flashcards
  - clrs
  - complexity
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "Provide the proof by induction for the relation #it(n) le log2 n + 1 for iterative..."
---

# 🎴 Provide the proof by induction for the relation #it(n) le log2 n + 1 for iterative...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: Provide the **proof by induction** for the relation $\#it(n) \le \log_2 n + 1$ for iterative binary search #card

?
We want to prove by induction on $n$ that $\#it(n) \le \log_2 n + 1$.

**BASE CASE:** $n = 1$
With only one element, exactly $1$ iteration is performed before terminating:

$$
\#it(1) = 1 \le \log_2 1 + 1 = 0 + 1 = 1
$$

The base case is verified.

**INDUCTIVE HYPOTHESIS:**
Assume that the relation holds for every size smaller than $n$:

$$
\forall k = 1, \dots, n-1 : \#it(k) \le \log_2 k + 1
$$

In the inductive step, at each iteration we halve the search space. The number of iterations on $n$ elements is given by the current iteration plus the iterations on the subproblem of residual size $\lfloor n/2 \rfloor$:

$$
\#it(n) \le 1 + \#it(\lfloor n/2 \rfloor)
$$

We distinguish based on the parity of $n$:

        1. **If $n$ is ODD:**

        Integer division $\lfloor n/2 \rfloor$ corresponds exactly to $\frac{n-1}{2}$. Since $\frac{n-1}{2} = \frac{n}{2} - \frac{1}{2}$, it trivially holds that:

$$
\lfloor n/2 \rfloor \le n/2
$$

        2. **If $n$ is EVEN:**

        Integer division $\lfloor n/2 \rfloor$ is exactly equal to $\frac{n}{2}$. We therefore have:

$$
\lfloor n/2 \rfloor = n/2
$$

In both cases, the size of the subproblem satisfies $\lfloor n/2 \rfloor \le n/2$.

Using the relation from the inductive step and applying the inductive hypothesis to $\lfloor n/2 \rfloor$ (since it is a size strictly smaller than $n$):

```text
{aligned} \#it(n)                    // ≤ 1 + \#it(floor( n / 2 ))
    // ≤ 1 + _2(floor( n / 2 )) + 1 (by inductive hypothesis)
    // ≤ 1 + _2(n/2) + 1 (since floor( n / 2 ) ≤ n/2 and is increasing)
// = 1 + _2 n - _2 2 + 1
// = 1 + _2 n - 1 + 1
// = _2 n + 1 {aligned}
```

The claim $\#it(n) \le \log_2 n + 1$ is therefore proven for all $n \ge 1$.
