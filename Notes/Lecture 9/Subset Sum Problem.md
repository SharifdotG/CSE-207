# **CSE 207 - Algorithms - Notes - Subset Sum Problem**

<p align="center">
    <img src="https://bytethisstore.com/assets/images/dev-articles/subset-sum-algorithm/preview.png" alt="Subset Sum Problem"/>
</p>

---

## **Introduction**

- The **Subset Sum Problem** is a classic problem in combinatorial optimization.
- Given a set of positive integers **S** and a target sum **T**, the goal is to find a subset of **S** that adds up to **T**.
- Let's consider an example:
  - **S = {3, 34, 4, 12, 5, 2}**
  - **T = 9**
  - The subset **{4, 5}** adds up to **9**.
- The **Subset Sum Problem** is an NP-hard problem.

---

## **Approximation Algorithm for Subset Sum Problem**

- The Approximation Algorithm for the **Subset Sum Problem** are as follows:
  - Sort the set **S** in non-decreasing order.
  - Include the largest element in the subset.
  - If the sum of the subset is less than **T**, include the next largest element.
  - Repeat the process until the sum of the subset is equal to **T** or the set is exhausted.
- S = {3, 34, 4, 12, 5, 2} and T = 9:
  - Approximation Algorithm output: {5, 4} = 9. Which is in this case the optimal solution.
- If all elements are in the set, the approximation algorithm will output the optimal solution.
- Or there is an output that does not add up to **T**.
  - In this case, The first input that does not fit is smaller than all previous inputs that are included in the subset.
  - The sum of elements in the subset is more than T/2 (because if the element is less than T/2, it would have been included in the subset).
  - If the sum is greater than T/2 then it’s obviously more than T/2.
- Therefore, the approximation algorithm is a 1/2-approximation algorithm for the **Subset Sum Problem**.
