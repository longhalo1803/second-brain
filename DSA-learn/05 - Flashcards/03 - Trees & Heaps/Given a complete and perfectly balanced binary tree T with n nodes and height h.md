---
title: "Given a complete and perfectly balanced binary tree T with n nodes and height h"
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
  - "Given a complete and perfectly balanced binary tree T with n nodes and height h"
---

# 🎴 Given a complete and perfectly balanced binary tree T with n nodes and height h

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: ❓ Given a complete and perfectly balanced binary tree $T$ with $n$ nodes and height $h$:

- prove by induction that $T$ has exactly $2^h$ leaves;
- (using the previous result) prove that $n = 2^{h+1} - 1$. #card
  ?
- **Proof by induction on the number of leaves ($L(h) = 2^h$):**
- **Base Case ($h=0$):** A tree of height $0$ consists of a single node, which is both the root and a leaf. The number of leaves is $1$. Checking the formula: $2^0 = 1$. The base case holds.
- **Inductive Hypothesis:** Assume that every complete and perfectly balanced binary tree of height $h-1$ has exactly $2^{h-1}$ leaves.
- **Inductive Step (height $h \ge 1$):** A complete and perfectly balanced binary tree of height $h$ consists of a root connected to two subtrees (left and right), both of which are complete and perfectly balanced with height $h-1$.
  By the inductive hypothesis, both the left and right subtrees contain $2^{h-1}$ leaves each. Since the leaves of the whole tree are the disjoint union of the leaves of the two subtrees, we have:

$$

L(h) = L*{\text{left}}(h-1) + L*{\text{right}}(h-1) = 2^{h-1} + 2^{h-1} = 2 \cdot 2^{h-1} = 2^h

$$

The claim is thus proven by induction.

- **Proof that $n = 2^{h+1} - 1$:**
  In a complete and perfectly balanced binary tree, every level $i$ (with $0 \le i \le h$) is completely filled. Because restricting the tree up to level $i$ forms a complete and balanced tree of height $i$, by part 1 it follows that the number of nodes at level $i$ is exactly $2^i$.
  The total number of nodes $n$ is the sum of nodes across all levels from $0$ to $h$:

$$

n = \sum\_{i=0}^{h} 2^i

$$

Recognizing the sum of a geometric series with common ratio $q = 2$:

$$

\sum\_{i=0}^{h} q^i = \frac{q^{h+1} - 1}{q - 1} \implies n = \frac{2^{h+1} - 1}{2 - 1} = 2^{h+1} - 1

$$
