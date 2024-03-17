# **CSE 207 - Algorithms - Notes - Fibonacci Series**

<p align="center">
    <img src="https://upload.wikimedia.org/wikipedia/commons/1/1a/Fibonacci_call_tree_5.gif" alt="Fibonacci Series"/>
</p>

---

## **Introduction**

- **Fibonacci Series** is a series of numbers in which each number is the sum of the two preceding ones, usually starting with 0 and 1.
- The sequence of numbers is:
  - 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, ...
- The sequence is named after **Leonardo of Pisa**, who was known as **Fibonacci**.
- The sequence is also known as the **Golden Ratio** and **Golden Spiral**.
- Fibonacci Series recurrence relation is given by:
  - `F(n) = F(n-1) + F(n-2)` for `n > 1`
  - `F(0) = 0`
  - `F(1) = 1`

---

## **Fibonacci Series - Naive Approach**

- The **Naive Approach** to solve the **Fibonacci Series** is to use **Recursion**.
- The **Naive Approach** has an **exponential time complexity**.
- The **Naive Approach** has a **time complexity** of `O(2^n)`.
- The **Naive Approach** has a **space complexity** of `O(n)`.
- The **Naive Approach** has a **recurrence relation** of `T(n) = T(n-1) + T(n-2) + 1`.
- The **Naive Approach** has a **recurrence tree** that grows exponentially.
- The **Naive Approach** has a **recurrence tree** that has overlapping subproblems.

<p align="center">
    <img src="https://avikdas.com/assets/images/2019-04-15-visual-introduction-to-dynamic-programming/fibonacci-naive.png" alt="Fibonacci Series - Naive Approach - Recurrence Tree"/>
</p>

```cpp
int fibonacci(int n) {
    if (n <= 1) {
        return n;
    }
    return fibonacci(n-1) + fibonacci(n-2);
}
```

- For each call to `fibonacci(n)`, there are two recursive calls to `fibonacci(n-1)` and `fibonacci(n-2)`.
- Each recursive call has two more recursive calls, and so on.
- As a result, the number of recursive calls grows exponentially.
- The **Naive Approach** has a **time complexity** of `O(2^n)`.

---

## **Fibonacci Series - Dynamic Programming**

- With **Dynamic Programming**, we can solve the **Fibonacci Series** in a more efficient way.
- We can solve the **Fibonacci Series** using **Dynamic Programming** in two ways:
  - **Memoization**: A technique used to store the results of the subproblems so that they can be utilized later on.
  - **Tabulation**: A technique used to store the results of the subproblems in a table so that they can be utilized later on.
- **Dynamic Programming** solves the **Fibonacci Series** in a more efficient way by solving each subproblem only once and saving its answer in a table, thereby avoiding the work of recomputing the answer every time the subproblem is encountered.

<p align="center">
    <img src="https://i.pinimg.com/originals/9a/5f/bf/9a5fbfa150fdeab90a3fd4c39afedf54.gif" alt="Fibonacci Series - Dynamic Programming - Recurrence Tree"/>
</p>

---

## **Algorithm**

1. Create a table `dp[]` of size `n+1` to store the results of the subproblems.
2. Initialize the first two elements of the table `dp[]` as `0` and `1`.
3. For each element `i` from `2` to `n`, calculate the value of `dp[i]` as the sum of `dp[i-1]` and `dp[i-2]`.
4. Return the value of `dp[n]`.
5. The base case of the recursion is when `n` is `0` or `1`.

### **Pseudocode**

```cpp
int fibonacci(int n) {
    int dp[n+1];

    dp[0] = 0;
    dp[1] = 1;

    for (int i = 2; i <= n; i++) {
        dp[i] = dp[i-1] + dp[i-2];
    }

    return dp[n];
}
```

---

## **Naive Approach vs Dynamic Programming**

| **Naive Approach** | **Dynamic Programming** |
|---|---|
| Exponential Time Complexity | Linear Time Complexity |
| Exponential Space Complexity | Linear Space Complexity |
| Recurrence Tree | No Recurrence Tree |
| Overlapping Subproblems | No Overlapping Subproblems |
| Recursion | No Recursion |
| Top-Down Approach | Bottom-Up Approach |
| Slow | Fast |
| Inefficient | Efficient |

---

## **Complexity Analysis**

- **Time Complexity**:
  - Best Case: `O(1)`
  - Average Case: `O(n)`
  - Worst Case: `O(n)`
- **Space Complexity**: `O(n)`

---

## **Simulation/Visualization**

<p align="center">
    <img src="https://www.simplilearn.com/ice9/free_resources_article_thumb/Fibonacci_Series_Tabular_Representation.gif" alt="Fibonacci Series - Dynamic Programming"/>
</p>

- **Web Based Resources**:
  - [**GeeksforGeeks**](https://www.geeksforgeeks.org/program-for-nth-fibonacci-number/)
  - [**Baeldung**](https://www.baeldung.com/cs/fibonacci-top-down-vs-bottom-up-dynamic-programming)
  - [**Medium**](https://elishevaelbaz.medium.com/solving-fibonacci-numbers-using-dynamic-programming-ee75ea708b7b)

- **Video Resources**:
  - [**4 Principle of Optimality - Dynamic Programming introduction - Abdul Bari**](https://www.youtube.com/watch?v=5dRGRueKU3M)
  - [**Dynamic Programming Tutorial with Fibonacci Sequence - CS Dojo**](https://www.youtube.com/watch?v=e0CAbRVYAWg)
  - [**Program for Fibonacci numbers using Dynamic Programming | GeeksforGeeks - GeeksforGeeks**](https://www.youtube.com/watch?v=LwZRsM7qhrI)

---
