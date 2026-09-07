---
title: "What are the main differences and ideal use cases between Kruskal's algorithm and..."
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
  - "What are the main differences and ideal use cases between Kruskal's algorithm and..."
---

# 🎴 What are the main differences and ideal use cases between Kruskal's algorithm and...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What are the main differences and ideal use cases between Kruskal's algorithm and Prim's algorithm? #card

?
FeatureKruskal's AlgorithmPrim's Algorithm**Approach**Centered on **edges** (merges disjoint components)Centered on **nodes** (expands a continuous tree)**Key Data Structure**Disjoint Set (Union-Find) + SortingPriority Queue (Min-Heap / Fibonacci Heap)**Complexity (standard)**$O(|E| \log |V|)$$O(|E| \log |V|)$ (with Min-Heap)
$O(|E| + |V| \log |V|)$ (with Fib-Heap)**Best performance on\*\***Sparse Graphs** ($|E| \ll |V|^2$). If edges are already sorted, runs in near-linear time**Dense Graphs\*\* ($|E| \approx |V|^2$), especially if implemented with a Fibonacci Heap
