# **CSE 207 - Algorithms - Notes - Dijkstra's Shortest Path Algorithm**

<p align="center">
    <img src="https://ds055uzetaobb.cloudfront.net/brioche/uploads/lessons/dijkstra-EQ50NN.gif" alt="Dijkstra's Shortest Path Algorithm"/>
</p>

---

## **Introduction**

- **Dijkstra's Shortest Path Algorithm** is a graph traversal algorithm.
- It is used to find the shortest path from a source vertex to all other vertices in a graph.
- It is used to find the shortest path in a weighted graph.
- It is implemented using a **Priority Queue** data structure.
- It is used to find the shortest path in a weighted graph.
- It is used to solve puzzles and games like the **8-puzzle** and **Tic-Tac-Toe**.
- It is used to find the shortest path in a network of cities or roads.

---

## **Algorithm**

- The **Dijkstra's Shortest Path Algorithm** is as follows:
- **Input**:
  - A graph represented as an adjacency matrix or an adjacency list.
  - The starting vertex to begin the traversal.
  - A **Priority Queue** to keep track of the vertices.
- **Output**:
  - The shortest path from the starting vertex to all other vertices.

1. Initialize the distance array with **INFINITY** and the visited array with **false**.
2. Set the distance of the starting vertex to **0**.
3. For each vertex in the graph, do the following:
   - Find the vertex with the minimum distance from the starting vertex.
   - Mark the vertex as visited.
   - Update the distance of the adjacent vertices.
   - Repeat the process until all the vertices are visited.
   - The shortest path will be found using the distance array.
   - The vertices will be visited in the order of traversal.
4. The **Dijkstra's Shortest Path Algorithm** is complete when all the vertices are visited.
5. Print the distance array to find the shortest path.

## **Psuedocode**

- The **Pseudocode** for the **Dijkstra's Shortest Path Algorithm** is as follows:

```cpp
void dijkstra(int graph[5][5], int start) {
    int dist[5];
    bool visited[5];

    for (int i = 0; i < 5; i++) {
        dist[i] = INT_MAX;
        visited[i] = false;
    }

    dist[start] = 0;

    for (int i = 0; i < 5; i++) {
        int u = minDistance(dist, visited);

        visited[u] = true;

        for (int v = 0; v < 5; v++) {
            if (!visited[v] && graph[u][v] && dist[u] != INT_MAX && dist[u] + graph[u][v] < dist[v]) {
                dist[v] = dist[u] + graph[u][v];
            }
        }
    }

    printSolution(dist, 5);
}
```

---

## **Complexity Analysis**

- The time complexity of the **Dijkstra's Shortest Path Algorithm** is **O(V^2)**.
- The space complexity of the **Dijkstra's Shortest Path Algorithm** is **O(V)**.
- **V** is the number of vertices in the graph.

---

## **Simulation/Visualization**

<p align="center">
    <img src="https://blog.aos.sh/img/DAGIF.gif" alt="Dijkstra's Shortest Path Algorithm"/>
</p>

- **Web Based Resources**:
  - [**GeeksforGeeks**](https://www.geeksforgeeks.org/dijkstras-shortest-path-algorithm-greedy-algo-7/)
  - [**freeCodeCamp**](https://www.freecodecamp.org/news/dijkstras-shortest-path-algorithm-visual-introduction/)
  - [**Programiz**](https://www.programiz.com/dsa/dijkstra-algorithm)
  - [**Javatpoint**](https://www.javatpoint.com/dijkstras-algorithm)

- **Video Resources**:
  - [**3.6 Dijkstra Algorithm - Single Source Shortest Path - Greedy Method - Abdul Bari**](https://www.youtube.com/watch?v=XB4MIexjvY0)
  - [**Dijkstra's Shortest Path Algorithm | Graph Theory - WilliamFiset**](https://www.youtube.com/watch?v=pSqmAO-m7Lk)
  - [**Dijkstra's algorithm in 3 minutes - Michael Sambol**](https://www.youtube.com/watch?v=_lHSawdgXpI)
  - [**Graph Data Structure 4. Dijkstra’s Shortest Path Algorithm - Computer Science**](https://www.youtube.com/watch?v=pVfj6mxhdMw)
  - [**Dijkstras Shortest Path Algorithm Explained | With Example | Graph Theory - FelixTechTips**](https://www.youtube.com/watch?v=bZkzH5x0SKU)
  - [**How Dijkstra's Algorithm Works - Spanning Tree**](https://www.youtube.com/watch?v=EFg3u_E6eHU)

---
