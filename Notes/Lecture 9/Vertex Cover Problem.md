# **CSE 207 - Algorithms - Notes - Vertex Cover Problem**

<p align="center">
    <img src="https://upload.wikimedia.org/wikipedia/commons/1/12/VCexample.gif" alt="Vertex Cover Problem"/>
</p>

---

## **Introduction**

- The **Vertex Cover Problem** is a classic problem in combinatorial optimization.
- It is a problem in which we are given an undirected graph G = (V, E) and we need to find the smallest set of vertices such that each edge in the graph is incident to at least one vertex in the set.
- The **Vertex Cover Problem** is an NP-hard problem.
- The **Vertex Cover Problem** is a decision problem that asks whether there exists a vertex cover of size k or less.
- Applications of the **Vertex Cover Problem** include:
  - Network Design.
  - VLSI Design.
  - Database Query Optimization.
  - Computational Biology.
  - Social Network Analysis.

---

## **Approximation Algorithm for Vertex Cover Problem**

- The **Vertex Cover Problem** is an NP-hard problem, and finding the exact solution is computationally infeasible.
- We can find a 2-approximation algorithm for the **Vertex Cover Problem**. By repeatedly selecting an edge and adding its endpoints to the vertex cover, then removing all edges incident to these vertices, we can find a vertex cover that is at most twice the size of the optimal vertex cover.
- Approximate Algorithm:
  - Initialize an empty set C to store the vertex cover.
  - While there are edges in the graph:
    - Select an arbitrary edge (u, v) from the graph.
    - Add u and v to the vertex cover set C.
    - Remove all edges incident to u and v from the graph.
  - Repeat the process until there are no edges are covered in the graph.

---
