# **CSE 207 - Algorithms - Notes - Approximation Algorithms**

<p align="center">
    <img src="https://stemlounge.com/content/images/2021/06/animated_algorithms.gif" alt="Approximation Algorithms"/>
</p>

---

## **Introduction**

- **Approximation Algorithms** are algorithms that find approximate solutions to optimization problems.
- They are used when finding the exact solution is computationally infeasible.
- Imagine you are given a very hard problem to solve, and you need to find a solution quickly. Unfortunately, you cannot find the exact solution in a reasonable amount of time. This is where **Approximation Algorithms** come in handy.
- What can be done in that case is to find an approximate solution that is close to the optimal solution. You can settle for a solution that is not perfect but is good enough for practical purposes. The solution could be almost perfect in polynomial time.
- It finds approximate solutions to NP-hard problems with provable guarantees on the quality of the solution.
- **Approximation Algorithms** are used in various fields such as computer science, mathematics, operations research scheduling, routing, and packing.

---

## **Approximation Ratio**

- There is way to tell if an **Approximation Algorithm** is good or bad.
- The **Approximation Ratio** is a measure of how good an **Approximation Algorithm** is.
- It is the ratio of the value of the solution produced by the **Approximation Algorithm** to the value of the optimal solution.
- Let C be the cost of the solution produced by the **Approximation Algorithm** and Let C* be the cost of the optimal solution.
- The **Approximation Ratio** ρ(n) of an approximation algorithm is the ratio between C and C*.
  - For minimization problems, the **Approximation Ratio** is defined as:
    - `0 <= C* <= C` and `C / C* <= ρ(n)`.
  - For maximization problems, the **Approximation Ratio** is defined as:
    - `0 <= C <= C*` and `C* / C <= ρ(n)`.
- An n-approximation algorithm is the result of an algorithm that produces a solution whose cost is at most n times the cost of the optimal solution.

---

## **Facts About Approximation Algorithms**

- It runs in polynomial time.
- Has a performance guarantee (By the **Approximation Ratio**).
- Each approximation algorithm is different, depending on the problem.
- Approximation Algorithms design techniques include:
  - Greedy Algorithms.
  - Dynamic Programming.
  - Linear Programming.
  - Randomized Algorithms.
  - Local Search.
