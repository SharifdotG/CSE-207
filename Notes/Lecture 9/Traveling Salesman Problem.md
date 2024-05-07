# **CSE 207 - Algorithms - Notes - Traveling Salesman Problem**

<p align="center">
    <img src="https://i.makeagif.com/media/4-25-2016/UZrVqj.gif" alt="Traveling Salesman Problem"/>
</p>

---

## **Introduction**

- The **Traveling Salesman Problem (TSP)** is a classic problem in combinatorial optimization.
- It is a problem in which a salesman has to visit a set of cities and return to the starting city.
- The goal is to find the shortest possible route that visits each city exactly once and returns to the starting city.
- The **Traveling Salesman Problem** is an NP-hard problem.

---

## **Using MST (Minimum Spanning Tree) to Solve TSP (Traveling Salesman Problem)**

- One way to solve the **Traveling Salesman Problem** is to use the **Minimum Spanning Tree (MST)**.
- Start by constructing an unweighted graph with the cities as vertices and the distances between the cities as edges.
- Find the **Minimum Spanning Tree** of the graph using **Kruskal's Algorithm** or **Prim's Algorithm**.
- Traverse the **Minimum Spanning Tree** in a depth-first manner to get a path that visits each vertex exactly once.
- Add the starting city to the end of the path (DFS traversal) to complete the cycle.

---
