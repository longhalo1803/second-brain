---
title: "Why does Algorithm 2 (DFS-based) work Show the analysis of edge types."
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
  - "Why does Algorithm 2 (DFS-based) work Show the analysis of edge types."
---

# 🎴 Why does Algorithm 2 (DFS-based) work Show the analysis of edge types.

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: Why does Algorithm 2 (DFS-based) work? Show the analysis of edge types. #card

?
During a DFS traversal on a directed graph, edges $(u,v)$ are classified into 4 categories. In DAGs, we observe that:

      Edge type $(u,v)$
      Relationship between finishing times `post`
      Position in the reverse ordering




      **Tree**
      $\text{post}[u] > \text{post}[v]$
      $u$ is to the left of $v$


      **Forward**
      $\text{post}[u] > \text{post}[v]$
      $u$ is to the left of $v$


      **Cross**
      $\text{post}[v]  \text{post}[v]$
      $u$ is to the left of $v$


      **Back**
      **Not present in DAGs!**
      -

Since $\text{post}[u] > \text{post}[v]$ holds for all allowed edges in a DAG, inserting nodes in decreasing order of `post[]` (i.e., by pushing onto a stack at the end of each visit) guarantees that for every edge $(u,v)$, node $u$ will always precede node $v$.

Static SVG
