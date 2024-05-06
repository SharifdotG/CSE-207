# **CSE 207 - Algorithms - Notes - Graph Coloring**

<p align="center">
    <img src="https://www3.cs.stonybrook.edu/~skiena/combinatorica/trias/peter.gif" alt="Graph Coloring"/>
</p>

---

## **Introduction**

- **Graph Coloring** is a classic problem in computer science.
- It is a combinatorial problem that involves coloring the vertices of a graph.
- The goal is to color the vertices in such a way that no two adjacent vertices have the same color.
- The problem is to find the minimum number of colors needed to color the vertices of a graph.
- The problem is solved using the **Greedy** technique.
- The Applications of **Graph Coloring** include scheduling, register allocation, and map coloring.

---

## **Vertex Coloring**

- **Vertex Coloring** is the process of assigning colors to the vertices of a graph.
- The colors are assigned in such a way that no two adjacent vertices have the same color.
- Given a graph **G** and a positive integer **m**, the goal is to find a **m-coloring** of the vertices of **G**. Or, find if the vertices of **G** can be colored in such a way that no two adjacent vertices have the same color yet using at most **m** colors are used.

---

## **Definitions**

- **Chromatic Number**: The **Chromatic Number** of a graph is the minimum number of colors needed to color the vertices of the graph.
- **K-Colorable**: A graph is **K-Colorable** if it can be colored using **K** colors.
- **Planar Graph**: A graph is **Planar** if it can be drawn on a plane without any edges crossing.
- **Four Color Theorem**: The **Four Color Theorem** states that any planar graph can be colored using at most four colors.

---

## **Algorithm**

- The **Graph Coloring** algorithm is as follows:
- **Input**:
  - A graph represented as an adjacency matrix or an adjacency list.
  - The vertices of the graph.
  - The edges of the graph.
  - A **Color Array** to keep track of the colors.
  - A **Coloring** to store the colors of the vertices.
  - A **Chromatic Number** to store the minimum number of colors.
  - A **Greedy** technique to color the vertices.
- Start with the first vertex and color it with the first color.
- Move to the next vertex and color it with the next color.
- Continue coloring the vertices until all vertices are colored.
- If a vertex has the same color as its adjacent vertex, change the color.
- Repeat the process until all vertices are colored.
- The **Graph Coloring** algorithm is complete when all vertices are colored.
- Print the **Coloring** and the **Chromatic Number**.
- The **Coloring** will be a subgraph of the original graph.
- The **Chromatic Number** will be the minimum number of colors needed.
- The vertices will be colored in the order of traversal.

---

## **Psuedocode**

- The **Pseudocode** for the **Graph Coloring** algorithm is as follows:

```cpp
void graph_coloring(int graph[5][5], int vertices[5], int edges[5][5]) {
    int colors[5];
    int coloring[5];
    int chromatic_number = 0;

    for (int i = 0; i < 5; i++) {
        colors[i] = 0;
        coloring[i] = 0;
    }

    for (int i = 0; i < 5; i++) {
        for (int j = 0; j < 5; j++) {
            if (edges[i][j] != 0) {
                coloring[i] = colors[j];
            }
        }
    }

    for (int i = 0; i < 5; i++) {
        if (coloring[i] > chromatic_number) {
            chromatic_number = coloring[i];
        }
    }

    cout << "Coloring: ";
    for (int i = 0; i < 5; i++) {
        cout << coloring[i] << " ";
    }
    cout << endl;

    cout << "Chromatic Number: " << chromatic_number << endl;
}
```

---

## **Complexity Analysis**

- The **Graph Coloring** algorithm has a time complexity of **O(m^v)**.
  - Where **m** is the number of colors and **v** is the number of vertices.
- Is also has a space complexity of **O(v)**.
  - Where **v** is the number of vertices in the graph.
- The algorithm uses a **Greedy** technique to color the vertices.
- This algorithm is okay for small graphs but not for large graphs.

---

## **Simulation/Visualization**

<p align="center">
    <img src="https://opensourc.es/assets/blog/2020-11-29-constraint-solver-coloring-cliques/images/simple_coloring.gif" alt="Graph Coloring"/>
</p>

- **Web Based Resources**:
  - [**GeeksforGeeks**](https://www.geeksforgeeks.org/graph-coloring-applications/)
  - [**Javatpoint**](https://www.javatpoint.com/chromatic-number-of-graphs-graph-coloring-in-graph-theory)

- **Video Resources**:
  - [**6.3 Graph Coloring Problem - Backtracking - Abdul Bari**](https://www.youtube.com/watch?v=052VkKhIaQ4)
  - [**Graph Colouring Problem - Backtracking - CSBreakdown**](https://www.youtube.com/watch?v=miCYGGrTwFU)
  - [**Graph Coloring | GeeksforGeeks - GeeksforGeeks**](https://www.youtube.com/watch?v=_sdVx_dWnlk)
  - [**Vertex Colorings and the Chromatic Number of Graphs | Graph Theory - Wraith of Math**](https://www.youtube.com/watch?v=3VeQhNF5-rE)

---
