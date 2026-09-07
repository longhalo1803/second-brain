---
title: "What is the computational complexity of BuildHeap(H) Compare the naive analysis wi..."
tags:
  - dsa
  - flashcards
  - clrs
  - trees-heaps
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "What is the computational complexity of BuildHeap(H) Compare the naive analysis wi..."
---

# 🎴 What is the computational complexity of BuildHeap(H) Compare the naive analysis wi...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What is the computational complexity of `BuildHeap(H)`? Compare the naive analysis with the accurate analysis. #card

?

- **Naive analysis**: Approximately $n/2$ calls to `Heapify` are performed, each costing $\mathcal{O}(\log n)$. This yields a loose upper bound of $\mathcal{O}(n \log n)$.
- **More accurate analysis**: The actual cost is $\mathcal{O}(n)$. `Heapify` is executed many times on very short heaps (near the leaves) and very few times on tall heaps (near the root). ***Formal proof**:
  A complete and perfectly balanced binary tree of height $h = \lfloor \log n \rfloor$ has $2^{h-\ell} = \left\lceil \frac{n}{2^{\ell+1}} \right\rceil$ internal nodes at level $h-\ell$ (for $\ell = 1, \dots, h$).

**Proof of the number of nodes:**
Since $n = 2^{h+1}-1$:

$$

\frac{n}{2^{\ell+1}} = \frac{2^{h+1}-1}{2^{\ell+1}} = \frac{2^{h+1}}{2^{\ell+1}} - \frac{1}{2^{\ell+1}} = 2^{h-\ell} - \frac{1}{2^{\ell+1}}

$$

$$

\left\lceil \frac{n}{2^{\ell+1}} \right\rceil = \left\lceil 2^{h-\ell} - \frac{1}{2^{\ell+1}} \right\rceil = 2^{h-\ell}

$$

since $2^{h-\ell}$ is an integer and $0 < \frac{1}{2^{\ell+1}} \le \frac{1}{4}$ for $\ell \ge 1$.

**Calculation of the time complexity:**
Summing the cost of `Heapify` across all nodes:

$$

\sum*{\ell=1}^{\lfloor \log n \rfloor} \left\lceil \frac{n}{2^{\ell+1}} \right\rceil \cdot \underbrace{\mathcal{O}(\ell)}*{\small\text{Heapify cost}} = \mathcal{O}\left( n \sum\_{\ell=2}^{\lfloor \log n \rfloor + 1} \frac{\ell}{2^\ell} \right) = \mathcal{O}(n)

$$

since the series converges to 2:

$$

\sum*{\ell=2}^{\lfloor \log n \rfloor + 1} \frac{\ell}{2^\ell} \le \sum*{\ell=2}^{\infty} \frac{\ell}{2^\ell} \le \sum\_{\ell=0}^{\infty} \ell \left( \frac{1}{2} \right)^\ell = \frac{1/2}{(1 - 1/2)^2} = 2

$$
