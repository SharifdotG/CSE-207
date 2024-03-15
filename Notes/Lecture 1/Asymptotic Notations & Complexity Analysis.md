# **CSE 207 - Algorithms - Notes - Asymptotic Notations & Complexity Analysis**

<p align="center">
    <img src="https://scaler.com/topics/images/graphical-representation-for-the-asymptotic-notations.webp" alt="Asymptotic Notations & Complexity Analysis">
</p>

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

<p align="center">
    <img src="https://cdn.kastatic.org/ka-perseus-images/501211c02f4c6765f60f23842450e1151cfd9c89.png" alt="O - Notation">
</p>

- The function g(n) appearing within the O() typically omits lower order terms and constant factors. For example, `O(n^2)` is the set of functions `f(n)` such that `f(n) ≤ cn^2` for some constant `c` and all `n ≥ n0` for some constant `n0`.
- Let's consider the following functions:
  - y1 = 3n^2 + 2n + 1
  - y2 = 6n^2 + 4n
  - y3 = 3n^2
- What is growth rate of each function?
  - y1 = O(n^2)
  - y2 = O(n^2)
  - y3 = O(n^2)
    - All of these equations are quadratic, but the constants and lower order terms are different.

---

## **Ω - Notation**

- When we only want to know the lower bound of an algorithm, we use Omega Notation.
- For a given function `g(n)`, we denote by `Ω(g(n))` the set of functions:
  - `Ω(g(n)) = { f(n): there exist positive constants c and n0 such that 0 ≤ cg(n) ≤ f(n) for all n ≥ n0 }`
  - `f(n)` is `Ω(g(n))` if and only if there exists a positive constant `c` and an integer constant `n0` such that `0 ≤ cg(n) ≤ f(n)` for all `n ≥ n0`. This is the formal definition of `Ω(g(n))`.
- For a sufficiently large `n`, the running time of an algorithm is at least `Ω(g(n))`.
- For example, the function `f(n) = 3n^2 + 2n + 1` is `Ω(n^2)` because `3n^2 + 2n + 1 ≥ 3n^2` for all `n ≥ 1`.

<p align="center">
    <img src="https://cdn.kastatic.org/ka-perseus-images/c02e6916d15bacae7a936381af8c6e5a0068f4fd.png" alt="Ω - Notation">
</p>

---

## **Θ - Notation**

- When we want to know both the upper and lower bounds of an algorithm, we use Theta Notation.
- For a given function `g(n)`, we denote by `Θ(g(n))` the set of functions:
  - `Θ(g(n)) = { f(n): there exist positive constants c1, c2, and n0 such that 0 ≤ c1g(n) ≤ f(n) ≤ c2g(n) for all n ≥ n0 }`
  - `f(n)` is `Θ(g(n))` if and only if there exist positive constants `c1`, `c2`, and an integer constant `n0` such that `0 ≤ c1g(n) ≤ f(n) ≤ c2g(n)` for all `n ≥ n0`. This is the formal definition of `Θ(g(n))`.
- For a sufficiently large `n`, the running time of an algorithm is between `c1g(n)` and `c2g(n)`.
- For example, the function `f(n) = 3n^2 + 2n + 1` is `Θ(n^2)` because `3n^2 + 2n + 1` is between `3n^2` and `6n^2` for all `n ≥ 1`.

<p align="center">
    <img src="https://cdn.kastatic.org/ka-perseus-images/c14a48f24cae3fd563cb3627ee2a74f56c0bcef6.png" alt="Θ - Notation">
</p>

---

## **Complexity Analysis**

- Complexity Analysis is the process of analyzing the time and space complexity of an algorithm.
- Based on the above three notations, we can analyze the time and space complexity of an algorithm.
- There are three types of complexity analysis:
  - **Best Case Complexity**: The minimum time or space taken by an algorithm. It is denoted by `T(n)`.
  - **Average Case Complexity**: The average time or space taken by an algorithm. It is denoted by `T(n)`.
  - **Worst Case Complexity**: The maximum time or space taken by an algorithm. It is denoted by `T(n)`.

<p align="center">
    <img src="https://learntocodetogether.com/wp-content/uploads/2019/08/download-1-1.png" alt="Complexity Analysis">
</p>

---

## **Complexity Analysis Between Two Algorithms**

### **Linear Search vs Binary Search**

<p align="center">
    <img src="https://www.mathwarehouse.com/programming/images/binary-vs-linear-search/binary-and-linear-search-animations.gif" alt="Binary Search Time Complexity">
</p>

- **Linear Search**

```cpp
int linearSearch(int arr[], int n, int target) {
    for (int i = 0; i < n; i++) {
        if (arr[i] == target) {
            return i;
        }
    }

    return -1;
}
```

- **Time Complexity**:
  - Best Case: `O(1)`
  - Average Case: `O(n)`
  - Worst Case: `O(n)`
- **Space Complexity**: `O(1)`

- **Binary Search**

```cpp
int binarySearch(int arr[], int n, int target) {
    int left = 0, right = n - 1;

    while (left <= right) {
        int mid = left + (right - left) / 2;

        if (arr[mid] == target) {
            return mid;
        } else if (arr[mid] < target) {
            left = mid + 1;
        } else {
            right = mid - 1;
        }
    }

    return -1;
}
```

- **Time Complexity**:
  - Best Case: `O(1)`
  - Average Case: `O(log n)`
  - Worst Case: `O(log n)`
- **Space Complexity**: `O(1)`

- **Comparison**:
  - In the best case, both algorithms have the same time complexity.
  - In the average and worst cases, the binary search algorithm is more efficient than the linear search algorithm.
  - The binary search algorithm has a time complexity of `O(log n)`, while the linear search algorithm has a time complexity of `O(n)`. This means that the binary search algorithm is more efficient than the linear search algorithm.

### A Look At How Can Analyze The Time Complexity of Binary Search

- In the beginning, the size of the array is `n`.
- After the first iteration, the size of the array becomes `n / 2`.
- After the second iteration, the size of the array becomes `n / 4` and so on.
- After the `k`th iteration, the size of the array becomes `n / 2^k`.
- When the size of the array becomes `1`, the algorithm stops.
  - `n / 2^k = 1`
  - => `2^k = n`
  - => `k = log n`

---
