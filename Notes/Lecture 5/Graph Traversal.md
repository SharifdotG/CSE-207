# **CSE 207 - Algorithms - Notes - Graph Traversal**

<p align="center">
    <img src="https://codeforces.com/predownloaded/8d/be/8dbe5d89e58b67f3d8e4d8e0e8eb3358ba921b28.png" alt="Graph Traversal"/>
</p>

---

## **Introduction**

- **Graph Traversal** is a technique used to visit all the vertices of a graph.
- It is used to explore and search the graph.
- There are two main components of a graph:
  - **Vertices (Nodes)**: Represented by circles.
    - Each vertex has a unique identifier.
    - The number of vertices is denoted by **V**.
    - The vertices are connected by edges.
  - **Edges (Connections)**: Represented by lines connecting the vertices.
    - The edges represent the relationship between the vertices.
    - The number of edges is denoted by **E**.
    - The edges can be directed or undirected.
    - The edges can have weights.
    - The edges can be represented as an adjacency matrix or an adjacency list.
    - The edges can be represented as a set of pairs or a set of triples

<p align="center">
    <img src="https://www.computersciencebytes.com/wp-content/uploads/2017/01/vertices_edges.png" alt="Graph Representation"/>
</p>

- **Graphs** can be classified into two types:
- **Directed Graphs (Digraphs)**: The edges have a direction.
  - The edges are represented as ordered pairs (u, v).
- **Undirected Graphs**: The edges do not have a direction.
  - The edges are represented as unordered pairs {u, v}.

<p align="center">
    <img src="https://media.geeksforgeeks.org/wp-content/uploads/20230731155550/file.png" alt="Graph Types"/>
</p>

- **Graphs** can also be classified into two types based on the presence of weights:
  - **Weighted Graphs**: The edges have weights.
  - **Unweighted Graphs**: The edges do not have weights.

<p align="center">
    <img src="https://i.ytimg.com/vi/cMijJ2C1TiI/maxresdefault.jpg" alt="Graph Weights"/>
</p>

---

## **Graph Representation**

- **Graphs** can be represented in two ways:
- **Adjacency List**: An array of lists where each list represents the edges of a vertex.
  - The array is of size **V** where **V** is the number of vertices.
  - The array is sparse for sparse graphs.
  - The array is dense for dense graphs.
- **Adjacency Matrix**: A 2D array of size **V x V** where **V** is the number of vertices.
  - The elements of the matrix represent the edges between the vertices.
  - The matrix is symmetric for undirected graphs.
  - The matrix is not symmetric for directed graphs.
  - The matrix is sparse for sparse graphs.
  - The matrix is dense for dense graphs.

<p align="center">
    <img src="https://media.geeksforgeeks.org/wp-content/uploads/20230727154843/Graph-Representation-of-Undirected-graph-to-Adjacency-List.png" alt="Adjacency List"/>
    <img src="https://media.geeksforgeeks.org/wp-content/uploads/20230727130528/Directed_to_Adjacency_matrix.png" alt="Adjacency List"/>
</p>

- **Connected Components**: A graph is said to be connected if there is a path between every pair of vertices.
  - A graph can have multiple connected components.
  - A graph can be disconnected.
  - An **Undirected Graph** is connected if there is a path between every pair of vertices.
  - A connected component of an undirected graph is a maximal set of vertices such that there is a path between every pair of vertices.

<p align="center">
    <img src="https://www.researchgate.net/publication/340015228/figure/fig1/AS:870805537845254@1584627627694/An-example-graph-with-3-connected-components.png" alt="Connected Components"/>
</p>

- **Trees**: A tree is a connected graph with no cycles.
  - **Tree**: A connected acyclic undirected graph.
  - **Forest**: A collection of trees. If an undirected graph is disconnected, it is a forest.
  - **Spanning Tree**: A subgraph of a graph that is a tree and contains all the vertices of the graph.

<p align="center">
    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRsEDHuBVIxhGQfFnZjQT5SLHFPcydY__R89fgz5Xo7gA&s" alt="Tree"/>
    <img src="https://static.javatpoint.com/tutorial/graph-theory/images/tree-and-forest1.png" alt="Spanning Tree"/>
    <img src="https://www.tutorialspoint.com/data_structures_algorithms/images/spanning_trees.jpg" alt="Minimum Spanning Tree"/>
</p>

---
