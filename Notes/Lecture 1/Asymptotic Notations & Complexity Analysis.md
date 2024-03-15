# **CSE 207 - Algorithms - Notes - Asymptotic Notations & Complexity Analysis**

---

## **Complexity of an Algorithm**

- **Time Complexity**: The amount of time an algorithm takes to solve a problem. It is a measure of the amount of time taken by an algorithm to execute as a function of the length of the input. It is denoted by T(n), where n is the size of the input. It is measured in terms of the number of basic operations performed by the algorithm. It is used to compare the efficiency of different algorithms for solving the same problem. It is expressed using the Big O notation. It is classified into different categories based on the input size. It is used to analyze the worst-case, best-case, and average-case scenarios of an algorithm. It is used to analyze the scalability of an algorithm.
- **Space Complexity**: The amount of memory an algorithm uses to solve a problem. It is a measure of the amount of memory used by an algorithm to execute as a function of the length of the input. It is denoted by S(n), where n is the size of the input. It is measured in terms of the number of memory cells used by the algorithm. It is used to compare the memory usage of different algorithms for solving the same problem. It is expressed using the Big O notation. It is classified into different categories based on the input size. It is used to analyze the worst-case, best-case, and average-case scenarios of an algorithm. It is used to analyze the scalability of an algorithm.

---

## **Asymptotic Notations**

- Asymptotic Notations are used to represent the time and space complexity of an algorithm.
- They are used to analyze the worst-case, best-case, and average-case scenarios of an algorithm.
- Asymptotic Notations are used to compare the efficiency of different algorithms for solving the same problem.
- Asymptotic notation gives us a method for classifying functions according to their rate of growth.
- The growth rate of a function is the rate at which the value of the function increases as the value of the input increases.

- There are a lot of Asymptotic Notations, but the most commonly used notations are Big O Notation, Omega Notation, and Theta Notation:
  - **Big O Notation**: It is used to represent the upper bound of an algorithm. It is used to represent the worst-case scenario of an algorithm. It is used to represent the maximum time or space taken by an algorithm. It is used to represent the efficiency of an algorithm. It is used to represent the scalability of an algorithm. It is used to represent the order of growth of an algorithm. It is used to represent the upper limit of an algorithm. It is used to represent the slowest rate of growth of an algorithm. It is used to represent the most significant term of an algorithm. It is used to represent the dominating term of an algorithm. It is used to represent the performance of an algorithm.
    - It is shown as `O(f(n))`, where `f(n)` is a function of `n`.
  - **Omega Notation**: It is used to represent the lower bound of an algorithm. It is used to represent the best-case scenario of an algorithm. It is used to represent the minimum time or space taken by an algorithm. It is used to represent the efficiency of an algorithm. It is used to represent the scalability of an algorithm. It is used to represent the order of growth of an algorithm. It is used to represent the lower limit of an algorithm. It is used to represent the fastest rate of growth of an algorithm. It is used to represent the least significant term of an algorithm. It is used to represent the dominated term of an algorithm. It is used to represent the performance of an algorithm.
    - It is shown as `Ω(f(n))`, where `f(n)` is a function of `n`.
  - **Theta Notation**: It is used to represent the average bound of an algorithm. It is used to represent the average-case scenario of an algorithm. It is used to represent the average time or space taken by an algorithm. It is used to represent the efficiency of an algorithm. It is used to represent the scalability of an algorithm. It is used to represent the order of growth of an algorithm. It is used to represent the average limit of an algorithm. It is used to represent the average rate of growth of an algorithm. It is used to represent the average significant term of an algorithm. It is used to represent the average performance of an algorithm.
    - It is shown as `Θ(f(n))`, where `f(n)` is a function of `n`.

- Though these notations are used to represent the time and space complexity of an algorithm, Big O Notation is the most commonly used notation.

---

## **O - Notation**

- When we only want to know the upper bound of an algorithm, we use Big O Notation.
- For a given function `g(n)`, we denote by `O(g(n))` the set of functions:
  - `O(g(n)) = { f(n): there exist positive constants c and n0 such that 0 ≤ f(n) ≤ cg(n) for all n ≥ n0 }`
  - `f(n)` is `O(g(n))` if and only if there exists a positive constant `c` and an integer constant `n0` such that `0 ≤ f(n) ≤ cg(n)` for all `n ≥ n0`. This is the formal definition of `O(g(n))`.
- For a sufficiently large `n`, the running time of an algorithm is at most `O(g(n))`.
- For example, the function `f(n) = 3n^2 + 2n + 1` is `O(n^2)` because `3n^2 + 2n + 1 ≤ 6n^2` for all `n ≥ 1`.
