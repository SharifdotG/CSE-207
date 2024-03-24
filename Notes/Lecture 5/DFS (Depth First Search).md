# **CSE 207 - Algorithms - Notes - DFS (Depth First Search)**

<p align="center">
    <img src="https://upload.wikimedia.org/wikipedia/commons/7/7f/Depth-First-Search.gif" alt="BFS (Breadth First Search)"/>
</p>

---

## **Introduction**

- **DFS (Depth First Search)** is a graph traversal algorithm.
- It is used to explore and search the graph.
- It visits all the vertices of the graph along a branch before backtracking.
- It is used to find the connected components and topological sorting in a graph.
- It is implemented using a **Stack** data structure or recursion.
- It is used to find the shortest path in a weighted graph.
- It is used to solve puzzles and games like the **8-puzzle** and **Tic-Tac-Toe**.

---

## **Algorithm**

- The **DFS (Depth First Search)** algorithm is as follows:
- **Input**:
  - A graph represented as an adjacency matrix or an adjacency list.
  - The starting vertex to begin the traversal.
  - A **Boolean** array to keep track of the visited vertices.
- **Output**:
  - The vertices visited in the order of traversal.

1. Print the starting vertex.
2. Mark the starting vertex as visited.
3. For each adjacent vertex of the starting vertex, do the following:
   - If the adjacent vertex is not visited, recursively call the **DFS** function on the adjacent vertex.
   - Repeat the process until all the vertices are visited.
   - The vertices will be visited in the order of traversal.
4. The **DFS (Depth First Search)** algorithm is complete when all the vertices are visited.

## **Pseudocode**

- The **Pseudocode** for the **DFS (Depth First Search)** algorithm is as follows:

```cpp
void dfs(int graph[5][5], int start, bool visited[5]) {
    cout << start << " ";
    visited[start] = true;

    for (int i = 0; i < 5; i++) {
        if (graph[start][i] == 1 && !visited[i]) {
            dfs(graph, i, visited);
        }
    }
}
```

---

## **Complexity Analysis**

- The time complexity of the **DFS (Depth First Search)** algorithm is **O(V + E)**.
- The space complexity of the **DFS (Depth First Search)** algorithm is **O(V)**.
- **V** is the number of vertices in the graph and **E** is the number of edges in the graph.

---

## **Simulation/Visualization**

<p align="center">
    <img src="https://inginious.org/course/competitive-programming/graphs-dfs/dfs.gif" alt="Graph Types"/>
</p>

- **Web Based Resources**:
  - [**GeeksforGeeks**](https://www.geeksforgeeks.org/depth-first-search-or-dfs-for-a-graph/)
  - [**Programiz**](https://www.programiz.com/dsa/graph-dfs)
  - [**HackerEarth**](https://www.hackerearth.com/practice/algorithms/graphs/depth-first-search/tutorial/)

- **Video Resources**:
  - [**5.1 Graph Traversals - BFS & DFS -Breadth First Search and Depth First Search - Abdul Bari**](https://www.youtube.com/watch?v=pcKY4hjDrxk)
  - [**Depth First Search Algorithm | Graph Theory - WilliamFiset**](https://www.youtube.com/watch?v=7fujbpJ0LB4)
  - [**Depth-first search in 4 minutes - Michael Sambol**](https://www.youtube.com/watch?v=Urx87-NMm6c)

---
