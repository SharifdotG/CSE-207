# **CSE 207 - Algorithms - Notes - Dynamic Programing**

<p align="center">
    <img src="https://lh3.googleusercontent.com/proxy/2cazcl9oV28r0cuVMGIv10fnviy31_3cUSqMtRuowKONPuoeHzwZVlLrIQGC7-j6tEwP8MRhKjre1zyIHvDagdckodNOSjZW" alt="Dynamic Programing"/>
</p>

---

## **Introduction**

- Dynamic Programming is a method for solving a complex problem by breaking it down into simpler subproblems.
- Unlike Divide and Conquer, Dynamic Programming solves each subproblem only once and saves its answer in a table, thereby avoiding the work of recomputing the answer every time the subproblem is encountered.
- DP Utilizes the concept of Memoization to store the results of the subproblems so that they can be utilized later on.
- It also utilizes the concept of Tabulation to store the results of the subproblems in a table so that they can be utilized later on.
- Dynamic Programming is a powerful technique that allows one to solve problems in a more efficient way.
- Dynamic Programming is a method for solving optimization problems.

---

## **Characteristics of Dynamic Programming**

- **Optimal Substructure**: A problem has an optimal substructure if an optimal solution can be constructed from optimal solutions of its subproblems.
- **Overlapping Subproblems**: A problem has overlapping subproblems if it can be broken down into subproblems which are reused several times.
- **Memoization**: A technique used to store the results of the subproblems so that they can be utilized later on.
- **Tabulation**: A technique used to store the results of the subproblems in a table so that they can be utilized later on.

---

## **Dynamic Programming vs. Divide and Conquer**

| **Dynamic Programming** | **Divide and Conquer** |
| --- | --- |
| Solves each subproblem only once | Solves each subproblem multiple times |
| Saves the answer of each subproblem | Recomputes the answer of each subproblem |
| Utilizes the concept of Memoization | Does not utilize the concept of Memoization |
| Utilizes the concept of Tabulation | Does not utilize the concept of Tabulation |
| Solves optimization problems | Solves decision problems |
| **Examples**: Fibonacci, Knapsack, Longest Common Subsequence, etc. | **Examples**: Merge Sort, Quick Sort, Binary Search, etc. |

---
