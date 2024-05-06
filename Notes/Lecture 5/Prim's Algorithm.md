# **CSE 207 - Algorithms - Notes - Prim's Algorithm**

<p align="center">
    <img src="https://upload.wikimedia.org/wikipedia/en/9/96/Prim-animation.gif" alt="Prim's Algorithm"/>
</p>

---

## **Introduction**

- **Prim's Algorithm** is a graph traversal algorithm.
- It is used to find the minimum spanning tree in a graph.
- It is used to find the minimum cost of connecting all the vertices in a graph.
- The minimum spanning tree is a subgraph of the original graph.
- Greedy algorithm is used to in the **Prim's Algorithm**.

---

## **Algorithm**

- The **Prim's Algorithm** is as follows:
- Start from a random vertex in the graph and add it to the **Minimum Spanning Tree**.
- Reapeat the following steps until all the vertices are part of the **Minimum Spanning Tree**:
  - Find the edge with the minimum weight among the edges connected to the vertices in the **Minimum Spanning Tree**.
  - If the edge connects a vertex that is not part of the **Minimum Spanning Tree**, add the edge and the vertex to the **Minimum Spanning Tree**.
- Return the **Minimum Spanning Tree**.

## **Psuedocode**

- The **Pseudocode** for the **Prim's Algorithm** is as follows:

```cpp
void prim(int graph[5][5], int edges[5][5]) {
    int mst[5][5];
    int weight = 0;

    for (int i = 0; i < 5; i++) {
        for (int j = 0; j < 5; j++) {
            mst[i][j] = 0;
        }
    }

    // Start from a random vertex
    mst[0][0] = 1;

    // Repeat until all vertices are part of the Minimum Spanning Tree
    while (/* All vertices are not part of the Minimum Spanning Tree */) {
        // Find the edge with the minimum weight
        // Add the edge and the vertex to the Minimum Spanning Tree
    }

    // Print the Minimum Spanning Tree and the Minimum Spanning Tree Weight
}
```

---

## **Complexity**

- The **Prim's Algorithm** has a time complexity of $O(V^2)$ for adjacency matrix and $O(E \log V)$ for adjacency list.
- The **Prim's Algorithm** has a space complexity of $O(V^2)$.
- The **Prim's Algorithm** is efficient for dense graphs.
- The **Prim's Algorithm** is not efficient for sparse graphs.

---

## **Simulation/Visualization**

<p align="center">
    <img src="https://i.stack.imgur.com/gMPmj.gif" alt="Dijkstra's Shortest Path Algorithm"/>
</p>

- **Web Based Resources**:
  - [**GeeksforGeeks**](https://www.geeksforgeeks.org/prims-minimum-spanning-tree-mst-greedy-algo-5/)
  - [**CP-Algorithms**](https://cp-algorithms.com/graph/mst_prim.html)
  - [**Programiz**](https://www.programiz.com/dsa/prim-algorithm)
  - [**Javatpoint**](https://www.javatpoint.com/prim-algorithm)

- **Video Resources**:
  - [**3.5 Prims and Kruskals Algorithms - Greedy Method - Abdul Bari**](https://www.youtube.com/watch?v=4ZlRH0eK-qQ)
  - [**Prim's Algorithm - Lalitha Natraj**](https://www.youtube.com/watch?v=5M7bOXrn54A)
  - [**Prim's algorithm in 2 minutes - Michael Sambol**](https://www.youtube.com/watch?v=cplfcGZmX7I)
  - [**Prim's Algorithm: Minimum Spanning Tree (MST) - EducateYouself**](https://www.youtube.com/watch?v=Uj47dxYPow8)

---
