# **CSE 207 - Algorithms - Notes - Greedy Algorithms**

<p align="center">
    <img src="https://www.simplilearn.com/ice9/free_resources_article_thumb/Source_to_Destination_Greedy_Algorithm_Solution.gif" alt="Greedy Algorithms"/>
</p>

---

## **Introduction**

- Greedy Algorithms is a method for solving optimization problems.
- It is an algorithmic paradigm that builds up a solution piece by piece, always choosing the next piece that offers the most immediate benefit.
- It is a mathematical process that finds the optimal solution at each stage with the hope of finding a global optimum. It determines which next step will provide the most immediate benefit, without regard to future consequences.
- Such algorithms are called greedy because while the optimal solution to each smaller instance will provide an immediate output, the algorithm doesn't consider the larger problem as a whole. This means that the algorithm makes its choices based on the current state of the problem without regard to the overall solution.
- It makes a locally optimal choice in the hope that this choice will lead to a globally optimal solution.
- It doesn't always produce the optimal solution, but it is often good enough and is much simpler and faster than other algorithms.

---

## **How To Decide Which Choice Is Optimal?**

- For any optimization, there are 2 key things:
  - An objective function that needs to be optimized.
  - A set of constraints that must be honored.

- Assume that you have an **objective function** and a **set of constraints**. The objective function is the function that you want to optimize. The constraints are the conditions that must be satisfied at a given point in time.
- A greedy algorithm makes a sequence of choices. At each step, it makes the choice that looks best at the moment. The choice made by a greedy algorithm may depend on choices made so far, but not on future choices or all the solutions to the subproblem.
- The greedy algorithm has only **one shot** to compute the optimal solution so that it never goes back and reverses the decision.

---

## **Greedy Choice Steps**

1. Make a greedy choice.
2. Create subproblems.
3. Solve each subproblem independently.
   - Continue the first 2 steps until you have solved all the subproblems.

---

## **Characteristics of Greedy Algorithms**

- **Greedy Choice Property**: A global optimum can be arrived at by selecting a local optimum.
- **Optimal Substructure**: A problem has an optimal substructure if an optimal solution can be constructed from optimal solutions of its subproblems.
- **Overlapping Subproblems**: A problem has overlapping subproblems if it can be broken down into subproblems which are reused several times.

---

## **Greedy Algorithms vs. Dynamic Programming**

| **Greedy Algorithms** | **Dynamic Programming** |
| --- | --- |
| Makes a sequence of choices | Solves each subproblem only once |
| Makes the choice that looks best at the moment | Saves the answer of each subproblem |
| Has only one shot to compute the optimal solution | Utilizes the concept of Memoization |
| Does not utilize the concept of Memoization | Utilizes the concept of Tabulation |
| Solves optimization problems | Solves optimization problems |
| **Examples**: Huffman Coding, Prim's Algorithm, Kruskal's Algorithm, etc. | **Examples**: Fibonacci, Knapsack, Longest Common Subsequence, etc. |

---
