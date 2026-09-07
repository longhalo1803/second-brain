---
title: "Given a graph with vertices V={1,2,3,4} and weighted edges (1,4)=1, (1,2)=8, (2,3)..."
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
  - "Given a graph with vertices V={1,2,3,4} and weighted edges (1,4)=1, (1,2)=8, (2,3)..."
---

# 🎴 Given a graph with vertices V={1,2,3,4} and weighted edges (1,4)=1, (1,2)=8, (2,3)...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 📝 Given a graph with vertices $V=\{1,2,3,4\}$ and weighted edges $(1,4)=1$, $(1,2)=8$, $(2,3)=1$, $(3,1)=4$, $(4,2)=2$, $(4,3)=9$:

- What is the initial matrix $D^{(0)}$ according to the Floyd-Warshall algorithm?
- How is the matrix $D^{(1)}$ computed from $D^{(0)}$ in the 4-node guided example of the Floyd-Warshall algorithm?
- What are the evolutions of matrices $D^{(2)}$, $D^{(3)}$ and the final matrix $D^{(4)}$ in the 4-node Floyd-Warshall example? #card
  ?
  ****1.****
  The initial matrix $D^{(0)}$ stores the weights of direct edges with no intermediate nodes ($k=0$):

D(0)1234108+$\infty$12+$\infty$01+$\infty$34+$\infty$0+$\infty$4+$\infty$290
**Initialization details:**

- Main diagonal: $D^{(0)}[i,i] = 0$ for all $i$.
- Cells with an existing edge: $D^{(0)}[1,2]=8$, $D^{(0)}[1,4]=1$, $D^{(0)}[2,3]=1$, $D^{(0)}[3,1]=4$, $D^{(0)}[4,2]=2$, $D^{(0)}[4,3]=9$.
- Cells without a direct edge: value $+\infty$.****2.****

To compute $D^{(1)}$, node 1 is enabled as an intermediate node ($k=1$). Row 1, column 1, and the diagonal remain identical to $D^{(0)}$.

**Computation of modified cells:**

- $D^{(1)}[3,2] = \min(D^{(0)}[3,2], D^{(0)}[3,1] + D^{(0)}[1,2]) = \min(+\infty, 4 + 8) = 12$
- $D^{(1)}[3,4] = \min(D^{(0)}[3,4], D^{(0)}[3,1] + D^{(0)}[1,4]) = \min(+\infty, 4 + 1) = 5$
- Other cells remain unchanged (e.g., $D^{(1)}[2,3] = 1$, $D^{(1)}[4,2] = 2$, $D^{(1)}[4,3] = 9$).**Resulting matrix $D^{(1)}$:**
  D(1)1234108+$\infty$12+$\infty$01+$\infty$3412054+$\infty$290
  📝 Example: To go from 3 to 4 passing through 1, the cost is $4 + 1 = 5$, improving upon the previous value $+\infty$.

****3.****
**Step $k = 2$ (enables node 2):**
Improves cell $D^{(2)}[1,3] = \min(+\infty, D^{(1)}[1,2] + D^{(1)}[2,3]) = \min(+\infty, 8 + 1) = 9$. It also improves $D^{(2)}[4,3] = \min(9, D^{(1)}[4,2] + D^{(1)}[2,3]) = \min(9, 2 + 1) = 3$.

**Step $k = 3$ (enables node 3):**
Improves various cells by passing through node 3, such as $D^{(3)}[2,1] = \min(+\infty, 1 + 4) = 5$, $D^{(3)}[2,4] = \min(+\infty, 1 + 5) = 6$, and $D^{(3)}[4,1] = \min(+\infty, 3 + 4) = 7$.

**Step $k = 4$ (enables node 4 - final matrix $D^{(4)}$):**
Further improves routes passing through 4 (e.g., $D^{(4)}[1,2] = \min(8, 1+2) = 3$, $D^{(4)}[1,3] = \min(9, 1+3) = 4$, $D^{(4)}[3,2] = \min(12, 5+2) = 7$).

**Final shortest distance matrix $D^{(4)}$:**
D(4)123410341250163470547230
