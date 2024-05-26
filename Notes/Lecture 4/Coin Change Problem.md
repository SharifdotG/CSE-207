# **CSE 207 - Algorithms - Notes - Coin Change Problem**

<p align="center">
    <img src="https://upload.wikimedia.org/wikipedia/commons/d/da/Greedy_algorithm_36_cents.svg" alt="Coin Change Problem"/>
</p>

---

## **Introduction**

- **Coin Change Problem** is a problem in combinatorial optimization.
- It is similar to the **Fractional Knapsack Problem**. But, in this problem, the items are coins of different denominations, and we have to make a change of a certain amount using the minimum number of coins.
- The **Coin Change Problem** is a classic problem in computer science and is used in various applications such as vending machines, currency exchange, and financial software.
- This problem can be solved using **Dynamic Programming** and **Greedy Algorithm**.
- In this note, we will discuss the **Greedy Algorithm** to solve the **Coin Change Problem**.

---

## **Coin Change Problem - Greedy Approach**

- Suppose we have a variety of coins consisting of **50**, **25**, **10**, **5**, and **1** denominations. Note that all these coins are integer values.
- We want to make a change of **63** using the minimum number of coins.
- The Optimal Solution is to use one **50**, one **10**, and three **1** coins, which makes a total of **3** coins.
- The output will be [1, 0, 1, 0, 3].

---

## **Solution Steps**

1. **Make greedy choices:** Choose the largest denomination coin that is less than or equal to the remaining amount. If there is no such coin, move to the next smaller denomination coin.
2. **Create subproblems:** Reduce the remaining amount by the chosen coin and repeat the process until the remaining amount becomes **0**.
3. **Solve subproblems:** Count the number of coins chosen at each step and return the total number of coins chosen.

---

## **Algorithm**

- The **Greedy Algorithm** to solve the **Coin Change Problem** is as follows:

0. Sort the coins in descending order.
1. If the amount is **0**, return **0**.
2. If the denomination of the coin is greater than the amount, move to the next smaller denomination coin.
3. Otherwise, add the coin to the change and reduce the amount by the denomination of the coin.
4. Repeat the process until the amount becomes **0**.
5. Return the total number of coins chosen.
6. End.

---

## **Pseudocode**

- The **Pseudocode** for the **Greedy Algorithm** to solve the **Coin Change Problem** is as follows:

```cpp
CoinChange(int coins[], int amount, int index) {
    if (amount == 0) {
        return 0;
    }

    if (coins[index] > amount) {
        return CoinChange(coins, amount, index + 1);
    }

    return 1 + CoinChange(coins, amount - coins[index], index);
}
```

- The **Pseudocode** chooses the largest denomination coin that is less than or equal to the remaining amount and reduces the remaining amount by the chosen coin until the remaining amount becomes **0**.
- The total number of coins chosen is then returned.
- The **Pseudocode** uses **Recursion** to solve the **Coin Change Problem**.
- The **Pseudocode** has a time complexity of **O(n)**, where **n** is the number of coins.

---

## **Complexity Analysis**

- Best Case Time Complexity: **O(n)**
- Average Case Time Complexity: **O(n)**
- Worst Case Time Complexity: **O(n)**
- Space Complexity: **O(1)**

- Sorting the coins in descending order takes **O(mlogn)** time.
- Overall time complexity is **O(mlogn) + O(n)**.
- As **m** is significantly small, the overall time complexity is **O(n)**.

---

## **Simulation/Visualization**

<p align="center">
    <img src="https://www.codesdope.com/staticroot/images/algorithm/greedy.gif" alt="Coin Change Problem - Greedy Algorithm"/>
</p>

- **Web Based Resources**:
  - [**GeeksforGeeks**](https://www.geeksforgeeks.org/greedy-algorithm-to-find-minimum-number-of-coins/)
  - [**Log2Base2**](https://www.log2base2.com/algorithms/greedy/greedy-algorithm.html)
  - [**CodesDope**](https://www.codesdope.com/course/algorithms-greedy-algorithm/)

- **Video Resources**:
  - [**Minimum Coins | Greedy Algorithms - take U forward**](https://www.youtube.com/watch?v=mVg9CfJvayM)
  - [**Greedy Algorithm to find minimum number of Coins | GeeksforGeeks - GeeksforGeeks**](https://www.youtube.com/watch?v=KTaEeTWRwgg)

---
