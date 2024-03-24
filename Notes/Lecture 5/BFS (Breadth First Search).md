# **CSE 207 - Algorithms - Notes - BFS (Breadth First Search)**

<p align="center">
    <img src="https://upload.wikimedia.org/wikipedia/commons/5/5d/Breadth-First-Search-Algorithm.gif" alt="BFS (Breadth First Search)"/>
</p>

---

## **Introduction**

- **BFS (Breadth First Search)** is a graph traversal algorithm.
- It is used to explore and search the graph.
- It visits all the vertices of the graph at the same level before moving to the next level.
- It is used to find the shortest path and connected components in an unweighted graph.
- It is implemented using a **Queue** data structure.

---

## **Algorithm**

- The **BFS (Breadth First Search)** algorithm is as follows:
- **Input**:
  - A graph represented as an adjacency matrix or an adjacency list.
  - The starting vertex to begin the traversal.
- **Output**:
  - The vertices visited in the order of traversal.

1. Create a **Queue** data structure to store the vertices.
2. Create a **Boolean** array to keep track of the visited vertices.
3. Initialize the **Queue** and the **Boolean** array.
4. Push the starting vertex into the **Queue** and mark it as visited.
5. While the **Queue** is not empty, do the following:
   - Dequeue a vertex from the **Queue**.
   - Visit the vertex.
   - For each adjacent vertex of the dequeued vertex, do the following:
     - If the adjacent vertex is not visited, enqueue it and mark it as visited.
   - Repeat the process until the **Queue** is empty.
   - The vertices will be visited in the order of traversal.
6. The **BFS (Breadth First Search)** algorithm is complete when all the vertices are visited.

---

## **Pseudocode**

- The **Pseudocode** for the **BFS (Breadth First Search)** algorithm is as follows:

```cpp
void bfs(int graph[5][5], int start) {
    queue<int> q;
    bool visited[5] = {false};

    q.push(start);
    visited[start] = true;

    while (!q.empty()) {
        int node = q.front();
        q.pop();

        cout << node << " ";

        for (int i = 0; i < 5; i++) {
            if (graph[node][i] == 1 && !visited[i]) {
                q.push(i);
                visited[i] = true;
            }
        }
    }
}
```

---

## **Complexity Analysis**

- The **BFS (Breadth First Search)** algorithm has the following time complexity:
  - The time complexity is **O(V + E)** where **V** is the number of vertices and **E** is the number of edges.
  - The algorithm visits each vertex and edge once.
  - The space complexity is **O(V)** where **V** is the number of vertices.
  - The algorithm uses a **Queue** data structure to store the vertices.
  - The space complexity can be **O(V + E)** if the graph is represented as an adjacency list.
  - The space complexity can be **O(V^2)** if the graph is represented as an adjacency matrix.

---

## **Simulation/Visualization**

<p align="center">
    <img src="https://aquarchitect.github.io/swift-algorithm-club/Breadth-First%20Search/Images/AnimatedExample.gif" alt="Graph Types"/>
</p>

- **Web Based Resources**:
  - [**GeeksforGeeks**](https://www.geeksforgeeks.org/breadth-first-search-or-bfs-for-a-graph/)
  - [**Programiz**](https://www.programiz.com/dsa/graph-bfs)
  - [**HackerEarth**](https://www.hackerearth.com/practice/algorithms/graphs/breadth-first-search/tutorial/)

- **Video Resources**:
  - [**5.1 Graph Traversals - BFS & DFS -Breadth First Search and Depth First Search - Abdul Bari**](https://www.youtube.com/watch?v=pcKY4hjDrxk)
  - [**Breadth First Search Algorithm | Shortest Path | Graph Theory - WilliamFiset**](https://www.youtube.com/watch?v=oDqjPvD54Ss)
  - [**Breadth-first search in 4 minutes - Michael Sambol**](https://www.youtube.com/watch?v=HZ5YTanv5QE)

---
