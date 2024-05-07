# **CSE 207 - Algorithms - Notes - Branch and Bound**

<p align="center">
    <img src="https://upload.wikimedia.org/wikipedia/commons/3/3c/Branchbound.gif" alt="Branch and Bound"/>
</p>

---

## **Introduction**

- **Branch and Bound** is a general algorithm design paradigm for solving optimization problems.
- It is a systematic method for finding the optimal solution of a problem.
- The word **Branch** refers to the fact that the algorithm constructs a tree of subproblems to be solved.
- The word **Bound** refers to the fact that the algorithm uses the bounds of the subproblems to prune the search space.
- A **Boundin** function is used to determine whether a node should be expanded or pruned.
- **State Space Tree** is a tree that represents the state space of a problem.
- In **Branch and Bound**, the state space tree is explored in a systematic way like **BFS** or **DFS**.

---

## **Terminology**

- **Live Node**: A node that has been generated but not yet expanded.
- **Dead Node**: A node that has been expanded.
- **E-node**: A node that has been expanded.
- **Cost Function**: A function that assigns a cost to each node.
  - Each node x in the search tree has a cost associated with it which helps in determining **E-node**. As **E-node** is the node with the least cost.
  - **C(x)** = cost of node x = **g(x)** + **h(x)**
    - **g(x)** = cost of reaching node x from the root node.
    - **h(x)** = estimated cost of reaching the goal node from node x.
- Three operations associated with the instance representation:
  - **Branch(I)** produces two or more instances that each represent a subset of S<sub>I</sub>
  - **Bound(I)** produces a lower bound on the cost of an optimal solution to S<sub>I</sub>. That is, it produces a number **b** such that **b ≤ c(x)** for all x in S<sub>I</sub>.
  - **IsSolution(I)** determines whether I represents a single candidate solution to S<sub>I</sub>.
