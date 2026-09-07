---
title: "1 Let T be a tree with n nodes. Answer the following questions, justifying your an..."
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
  - "1 Let T be a tree with n nodes. Answer the following questions, justifying your an..."
---

# 🎴 1 Let T be a tree with n nodes. Answer the following questions, justifying your an...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📝 1 Let $T$ be a tree with $n$ nodes. Answer the following questions, justifying your answers:

- How many edges does the tree have?
- What is the maximum height the tree can have?
- What is the minimum height the tree can have if $n > 1$?
- If the tree is binary, what is the minimum height it can have? #card
  ?
  **1. Number of edges:**
  A tree with $n$ nodes has exactly $n - 1$ edges. In fact, every node except the root has exactly one incoming edge coming from its parent.

**2. Maximum height:**
The maximum height is $n - 1$. It is obtained in the case of a degenerate tree (chain/path), where each node has only one child (except the single leaf).
In this case, we obtain what is called a chain (or path, which is a special case of a degenerate tree) and the height of the tree is exactly $n - 1$, which equals the number of edges in the tree.

**3. Minimum height (general tree with $n > 1$):**
The minimum height is $1$. It is obtained when all $n - 1$ nodes (other than the root) are direct children of the root.

**4. Minimum height (binary tree):**
Since each node has at most 2 children, the height is minimal when the tree is as balanced as possible (almost complete tree). The minimum height is $\lfloor \log_2 n \rfloor$, which is $\Theta(\log n)$.
