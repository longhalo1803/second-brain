---
title: "State and prove the Lower Bound Theorem for comparison sorting."
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
  - "State and prove the Lower Bound Theorem for comparison sorting."
---

# 🎴 State and prove the Lower Bound Theorem for comparison sorting.

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: State and prove the Lower Bound Theorem for comparison sorting. #card

?
Any sorting algorithm **based exclusively on comparisons** between elements must perform, in the worst case, **at least **$\boxed{\Omega(n \log n)}$** comparisons** to sort a sequence of $n$ elements.

**Proof (via permutation counting / decision tree):**

- Given $n$ distinct elements, the number of possible initial arrangements/orderings (permutations) is $n!$. The algorithm must identify the single correct permutation among the $n!$ possibilities.
- Each comparison between two elements (e.g., $A[i] \le A[j]$) has a binary outcome (True/False) and allows dividing the set of still admissible permutations $p_i$ into two groups: $p_{i\_OK}$ and $p_{i\_KO}$, such that $p_i = p_{i\_OK} + p_{i\_KO}$.
- In the **worst case**, the algorithm will have to proceed in the subset of larger size:

$$
p_{i+1} = \max\{p_{i\_OK}, p_{i\_KO}\} \ge \frac{p_i}{2}
$$

- Initially, before any comparison ($i=0$), we have $p_0 = n!$. After $i$ comparisons, in the worst case the remaining permutations are:

$$
p_i \ge \frac{n!}{2^i}
$$

- To uniquely determine the ordering, the set of possible permutations must be reduced to **exactly one** ($p_i = 1$):

$$
1 \ge \frac{n!}{2^i} \implies 2^i \ge n! \implies i \ge \log_2(n!)
$$

- **Estimation of **$\log_2(n!)$**:**
  Assuming $n$ is even and bounding the product to the first $n/2$ factors (each $> n/2$):

$$
\begin{aligned}n! &= n \cdot (n-1) \dots 2 \cdot 1 \\&\ge n \cdot (n-1) \dots \left(\frac{n}{2} + 1\right) > \left(\frac{n}{2}\right)^{\frac{n}{2}}\end{aligned}
$$

Taking the logarithm:

$$
i \ge \log_2(n!) > \log_2\left(\frac{n}{2}\right)^{\frac{n}{2}} = \frac{n}{2} \log_2\left(\frac{n}{2}\right) = \frac{n}{2}(\log_2 n - 1) \in \Omega(n \log n)
$$

Therefore, at least $\Omega(n \log n)$ comparisons are required in the worst case.
