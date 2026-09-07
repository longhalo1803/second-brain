---
title: "What do the pre and post arrays used during DFS traversal represent, and what is t..."
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
  - "What do the pre and post arrays used during DFS traversal represent, and what is t..."
---

# 🎴 What do the pre and post arrays used during DFS traversal represent, and what is t...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What do the `pre` and `post` arrays used during DFS traversal represent, and what is their purpose? #card

?
The `pre` and `post` arrays store the two time instances/events recorded via a **global counter `time` **during the DFS traversal:

- **`pre[u]`:** time instance at which node $u$ is "discovered" (its traversal begins).

- **`post[u]`:** time instance at which the traversal of node $u$ is "finished" (after visiting all its adjacent nodes).
  They allow precise classification of the nature of each edge $(u,v)$ (Tree, Back, Forward, Cross) in real time during the traversal execution.
  ⚠️ Warning: before the DFS traversal, `pre` and `post` are all initialized to 0. The first time instance starts at 1.

📝 Example:

⚠️ Warning:

The counter increments only at two moments:

- When entering a node for the first time (`pre`).

- When definitively exiting a node after finishing its traversal (`post`).
  Checking an already visited node does **not** increment the counter.
