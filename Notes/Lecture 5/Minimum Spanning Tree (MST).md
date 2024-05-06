# **CSE 207 - Algorithms - Notes - Minimum Spanning Tree (MST)**

<p align="center">
    <img src="https://www3.cs.stonybrook.edu/~skiena/combinatorica/animations/anim/mst.gif" alt="Minimum Spanning Tree"/>
</p>

---

## **Introduction**

- **Minimum Spanning Tree (MST)** is a tree that connects all the vertices of a graph with the minimum possible total edge weight.
- It is a subset of the edges of a connected, edge-weighted graph that connects all the vertices together without any cycles and with the minimum possible total edge weight.
- The **Minimum Spanning Tree** is used to find the minimum cost of connecting all the vertices of a graph.
- The **Minimum Spanning Tree** is used in various applications such as network design, circuit design, clustering, and clustering.
- The **Minimum Spanning Tree** is a special case of the **Spanning Tree**.
- Examples of **Minimum Spanning Tree** algorithms include **Kruskal's Algorithm** and **Prim's Algorithm**.

---

## **Properties**

- The **Minimum Spanning Tree** has the following properties:
  - It is a tree that connects all the vertices of a graph.
  - It has **V - 1** edges where **V** is the number of vertices.
  - It has no cycles.
  - It has the minimum possible total edge weight.
  - It is unique if the edge weights are unique.
  - It is not unique if the edge weights are not unique.
  - It is a subgraph of the original graph.
  - It is a connected graph.
  - It is an acyclic graph.

---

## **Minimum Spanning Tree - Naive Approach**

- The **Naive Approach** to find the **Minimum Spanning Tree** is to generate all the possible spanning trees of the graph and then select the one with the minimum total edge weight.
- The **Naive Approach** has a time complexity of **O(2^E)** where **E** is the number of edges. It is exponential and not feasible for large graphs.

---
