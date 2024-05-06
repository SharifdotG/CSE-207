# **CSE 207 - Algorithms - Notes - Kruskal's Algorithm**

<p align="center">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5c/MST_kruskal_en.gif/480px-MST_kruskal_en.gif" alt="Kruskal's Algorithm"/>
</p>

---

## **Introduction**

- **Kruskal's Algorithm** is a graph traversal algorithm.
- It is used to find the minimum spanning tree in a graph.
- It is used to find the minimum cost of connecting all the vertices in a graph.
- The minimum spanning tree is a subgraph of the original graph.
- Greedy algorithm is used to in the **Kruskal's Algorithm**.
- It is used in applications like network design and clustering.

---

## **Algorithm**

- The **Kruskal's Algorithm** is as follows:
- **Input**:
  - A graph represented as an adjacency matrix or an adjacency list.
  - The edges of the graph.
  - A **Priority Queue** to keep track of the edges.
  - A **Disjoint Set** to keep track of the vertices.
  - A **Minimum Spanning Tree** to store the edges.
  - A **Minimum Spanning Tree Weight** to store the weight of the tree.

1. Sort the edges of the graph in non-decreasing order of their weights.
2. Initialize the **Minimum Spanning Tree** and the **Minimum Spanning Tree Weight**.
3. For each edge in the graph, do the following:
   - Find the edge with the minimum weight.
   - Check if the edge forms a cycle in the **Minimum Spanning Tree**.
   - If the edge does not form a cycle, add it to the **Minimum Spanning Tree**.
   - Repeat the process until all the edges are visited.
   - The **Minimum Spanning Tree** will be found using the edges.
   - The **Minimum Spanning Tree Weight** will be found using the weights.
   - The edges will be visited in the order of traversal.

- The **Kruskal's Algorithm** is complete when all the edges are visited.
- Print the **Minimum Spanning Tree** and the **Minimum Spanning Tree Weight**.
- The **Minimum Spanning Tree** will be a subgraph of the original graph.

## **Psuedocode**

- The **Pseudocode** for the **Kruskal's Algorithm** is as follows:

```cpp
void kruskal(int graph[5][5], int edges[5][5]) {
    int mst[5][5];
    int weight = 0;

    for (int i = 0; i < 5; i++) {
        for (int j = 0; j < 5; j++) {
            mst[i][j] = 0;
        }
    }

    for (int i = 0; i < 5; i++) {
        for (int j = 0; j < 5; j++) {
            if (edges[i][j] != 0) {
                mst[i][j] = edges[i][j];
            }
        }
    }

    for (int i = 0; i < 5; i++) {
        for (int j = 0; j < 5; j++) {
            if (mst[i][j] != 0) {
                weight += mst[i][j];
            }
        }
    }

    cout << "Minimum Spanning Tree Weight: " << weight << endl;
}
```

---

## **Complexity Analysis**

- The **Kruskal's Algorithm** has the following complexities:
- Sorting **E** edges takes **O(E log E)** time.
- Selecting **E** edges takes **O(E)** time.
- Checking **V** vertices if it is in the same component takes **O(V log V)** time.
- As **E**<sub>**max**</sub> = **V**<sup>**2**</sup>, we can write **O(E log E) = O(V<sup>2</sup> log V)**.
- Overall the **Time Complexity** of the **Kruskal's Algorithm** is **O(E log V)**.
- The **Space Complexity** of the **Kruskal's Algorithm** is **O(V + E)**.
- The **Kruskal's Algorithm** is efficient for sparse graphs.
- The **Kruskal's Algorithm** is not efficient for dense graphs.

---

## **Simulation/Visualization**

<p align="center">
    <img src="https://thealgoristsblob.blob.core.windows.net/thealgoristsimages/kruskals-algorithm-anim-1.gif" alt="Dijkstra's Shortest Path Algorithm"/>
</p>

- **Web Based Resources**:
  - [**GeeksforGeeks**](https://www.geeksforgeeks.org/kruskals-minimum-spanning-tree-algorithm-greedy-algo-2/)
  - [**CP-Algorithms**](https://cp-algorithms.com/graph/mst_kruskal.html)
  - [**Programiz**](https://www.programiz.com/dsa/kruskal-algorithm)
  - [**Javatpoint**](https://www.javatpoint.com/kruskal-algorithm)

- **Video Resources**:
  - [**3.5 Prims and Kruskals Algorithms - Greedy Method - Abdul Bari**](https://www.youtube.com/watch?v=4ZlRH0eK-qQ)
  - [**Kruskal's Algorithm - Lalitha Natraj**](https://www.youtube.com/watch?v=ivcbaIhrcsE)
  - [**Kruskal's algorithm in 2 minutes - Michael Sambol**](https://www.youtube.com/watch?v=71UQH7Pr9kU)
  - [**Graph Data Structure 4. Dijkstra’s Shortest Path Algorithm - Computer Science**](https://www.youtube.com/watch?v=pVfj6mxhdMw)

---
