---
title: "How is the O(log n) complexity proven for Find-set and Union with the Rank Heuristic"
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
  - "How is the O(log n) complexity proven for Find-set and Union with the Rank Heuristic"
---

# 🎴 How is the O(log n) complexity proven for Find-set and Union with the Rank Heuristic

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: How is the O(log n) complexity proven for `Find-set` and `Union` with the Rank Heuristic? #card

?
**Proof of logarithmic complexity**:

1. By the Rank Proposition, every tree rooted at $r$ with $k$ nodes satisfies the relation $k \ge 2^{\textsf{rank}[r]}$.
2. Since the maximum size of any tree in the forest is at most the total number of nodes in the generative set ($k \le n$), it follows that:

```text
2^{rank[r]} ≤ k ≤ n rank[r] ≤ _2 n
```

3. The height of each tree in the forest is upper bounded by the rank of its root; therefore, the height is at most $\log_2 n$.
4. The traversal up to the root performed by `Find-set(DS, x)` traverses a path of length at most the height of the tree.

**Conclusion:**
The cost of `Find-set` is bounded by $O(\log n)$.
Consequently, the `Union` operation (which consists of two calls to `Find-set` followed by constant-time updates) also has a time complexity of $O(\log n)$.
