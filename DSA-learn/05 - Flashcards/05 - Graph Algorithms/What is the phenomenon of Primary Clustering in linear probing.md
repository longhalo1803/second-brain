---
title: "What is the phenomenon of Primary Clustering in linear probing"
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
  - "What is the phenomenon of Primary Clustering in linear probing"
---

# 🎴 What is the phenomenon of Primary Clustering in linear probing

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: What is the phenomenon of **Primary Clustering** in linear probing? #card

?
**Primary clustering** is a serious performance degradation problem typical of linear probing.

It occurs when consecutively occupied slots form long contiguous blocks (called _clusters_):

- Any new key whose initial hash index falls into the block (or immediately before it) will be appended to the end of that cluster.
- The longer a cluster gets, the higher the geometric probability that subsequent keys land inside the block, making it grow even faster.**Consequence:** average times for insertion, search, and deletion operations degrade noticeably, moving far away from constant time $O(1)$.
