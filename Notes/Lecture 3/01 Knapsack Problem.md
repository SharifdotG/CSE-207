# **CSE 207 - Algorithms - Notes - 0/1 Knapsack Problem**

<p align="center">
    <img src="https://cdn.hashnode.com/res/hashnode/image/upload/v1618450959080/2KfuBtauA.jpeg" alt="0/1 Knapsack Problem"/>
</p>

---

## **Introduction**

- **0/1 Knapsack Problem** is a problem in combinatorial optimization.
- **0/1 Knapsack Problem** is a problem in which a set of items, each with a weight and a value, are to be placed in a knapsack of a fixed capacity to obtain the maximum total value in the knapsack.
- In this problem, the items cannot be broken down into smaller pieces, and the thief cannot take a fraction of any item.
- The problem is called **0/1 Knapsack Problem** because for each item, the thief must either take the whole item or leave it.
- The problem is also known as the **Binary Knapsack Problem**.

---

## **0/1 Knapsack Problem - Brute Force Approach**

- The **Brute Force Approach** to solve the **0/1 Knapsack Problem** is to use **Recursion**.
- It has an **exponential time complexity**.
- It has a **time complexity** of `O(2^n)`.
- It has a **space complexity** of `O(n)`.
- It starts from the beginning and check it we can maximize the value by including the item or not including the item.

```cpp
int knapsack(int capacity, int weights[], int values[], int n) {
    if (n == 0 || capacity == 0) {
        return 0;
    }
    if (weights[n-1] > capacity) {
        return knapsack(capacity, weights, values, n-1);
    } else {
        return max(
            values[n-1] + knapsack(capacity-weights[n-1], weights, values, n-1),
            knapsack(capacity, weights, values, n-1)
        );
    }
}
```

- For each call to `knapsack(capacity, weights, values, n)`, there are two recursive calls to `knapsack(capacity-weights[n-1], weights, values, n-1)` and `knapsack(capacity, weights, values, n-1)`.
- Each recursive call has two more recursive calls, and so on.
- As a result, the number of recursive calls grows exponentially.
- The **Brute Force Approach** has a **time complexity** of `O(2^n)`.

---

## **0/1 Knapsack Problem - Dynamic Programming**

- With **Dynamic Programming**, we can solve the **0/1 Knapsack Problem** in a more efficient way.
- We can solve the **0/1 Knapsack Problem** using **Dynamic Programming** in two ways:
  - **Memoization**: A technique used to store the results of the subproblems so that they can be utilized later on.
  - **Tabulation**: A technique used to store the results of the subproblems in a table so that they can be utilized later on.
- **Dynamic Programming** solves the **0/1 Knapsack Problem** in a more efficient way by solving each subproblem only once and saving its answer in a table, thereby avoiding the work of recomputing the answer every time the subproblem is encountered.

---

## **Algorithm**

1. Create a table `dp[][]` of size `(n+1) x (capacity+1)` to store the results of the subproblems.
2. Initialize the first row and the first column of the table `dp[][]` as `0`.
3. For each element `i` from `1` to `n` and each element `w` from `1` to `capacity`, calculate the value of `dp[i][w]` as the maximum of:
   - `values[i-1] + dp[i-1][w-weights[i-1]]` if `weights[i-1] <= w`
   - `dp[i-1][w]` if `weights[i-1] > w`
4. Return the value of `dp[n][capacity]`.

---

## **Pseudocode**

```cpp
int knapsack(int weights[], int values[], int n, int capacity) {
    int dp[n + 1][capacity + 1];
    
    for (int i = 0; i <= n; i++) {
        for (int w = 0; w <= capacity; w++) {
            if (i == 0 || w == 0) {
                dp[i][w] = 0;
            } else if (weights[i - 1] <= w) {
                dp[i][w] = max(values[i - 1] + dp[i - 1][w - weights[i - 1]], dp[i - 1][w]);
            } else {
                dp[i][w] = dp[i - 1][w];
            }
        }
    }

    return dp[n][capacity];
}
```

- Here, `dp[i][w]` represents the maximum value that can be obtained with a knapsack capacity of `w` and `i` items.
- The base case of the recursion is when `i` is `0` or `w` is `0`.
- The value of `dp[n][capacity]` is the maximum value that can be obtained with a knapsack capacity of `capacity` and `n` items.
- The **Dynamic Programming Approach** has a **time complexity** of `O(n*capacity)`.

---

## **Tabulation**

- Suppose the weights of the items are `2`, `3`, `4`, and `5`.
- Suppose the values of the items are `3`, `4`, `5`, and `6`.
- Suppose the knapsack capacity is `5`.
- The table `dp[][]` is as follows:

  |   | 0 | 1 | 2 | 3 | 4 | 5 |
  | --- | --- | --- | --- | --- | --- | --- |
  | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
  | 1 | 0 | 0 | 3 | 3 | 3 | 3 |
  | 2 | 0 | 0 | 3 | 4 | 4 | 7 |
  | 3 | 0 | 0 | 3 | 4 | 5 | 7 |
  | 4 | 0 | 0 | 3 | 4 | 5 | 7 |

- The value of `dp[4][5]` is `7`.

---

## **Brute Force Approach vs Dynamic Programming**

| **Brute Force Approach** | **Dynamic Programming** |
| --- | --- |
| The **Brute Force Approach** to solve the **0/1 Knapsack Problem** is to use **Recursion**. | With **Dynamic Programming**, we can solve the **0/1 Knapsack Problem** in a more efficient way. |
| It has an **exponential time complexity**. | It has a **time complexity** of `O(n*capacity)`. |
| It has a **time complexity** of `O(2^n)`. | The **Dynamic Programming Approach** has a **time complexity** of `O(n*capacity)`. |
| It has a **space complexity** of `O(n)`. | It has a **space complexity** of `O(n*capacity)`. |

---

## **Complexity Analysis**

- The **Brute Force Approach** has a **time complexity** of `O(2^n)`.
- The **Dynamic Programming Approach** has a **time complexity** of `O(n*capacity)`.
- The **Dynamic Programming Approach** has a **space complexity** of `O(n*capacity)`.

---

## **Simulation/Visualization**

<p align="center">
    <img src="https://upload.wikimedia.org/wikipedia/commons/d/dc/Knapsack_problem_dynamic_programming.gif" alt="0/1 Knapsack Problem - Dynamic Programming"/>
</p>

- **Web Based Resources**:
  - [**GeeksforGeeks**](https://www.geeksforgeeks.org/0-1-knapsack-problem-dp-10/)
  - [**Javatpoint**](https://www.javatpoint.com/0-1-knapsack-problem)
  - [**Tutorialspoint**](https://www.tutorialspoint.com/data_structures_algorithms/01_knapsack_problem.htm)

- **Video Resources**:
  - [**4.5 0/1 Knapsack - Two Methods - Dynamic Programming - Abdul Bari**](https://www.youtube.com/watch?v=nLmhmB6NzcM)
  - [**0/1 Knapsack Problem Dynamic Programming - Tushar Roy - Coding Made Simple**](https://www.youtube.com/watch?v=8LusJS5-AGo)
  - [**4.5.1 0/1 Knapsack Problem (Program) - Dynamic Programming - Abdul Bari**](https://www.youtube.com/watch?v=zRza99HPvkQ)
  - [**0-1 Knapsack Problem (Dynamic Programming) - CS Dojo**](https://www.youtube.com/watch?v=xOlhR_2QCXY)

---
