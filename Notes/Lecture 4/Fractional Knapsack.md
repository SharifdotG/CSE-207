# **CSE 207 - Algorithms - Notes - Fractional Knapsack Problem**

<p align="center">
    <img src="https://www.boardinfinity.com/blog/content/images/2023/02/Fractional-Knapsack-Problem.png" alt="0/1 Knapsack Problem"/>
</p>

---

## **Introduction**

- **Fractional Knapsack Problem** is a problem in combinatorial optimization.
- It is similar to the **0/1 Knapsack Problem**. But, in this problem, the items can be broken down into smaller pieces, and we can take a fraction of any item.

---

## **Fractional Knapsack Problem - Greedy Approach**

- The **Greedy Approach** to solve the **Fractional Knapsack Problem** is to use **Greedy Algorithm**.
- The **Greedy Algorithm** is an algorithmic paradigm that builds up a solution piece by piece, always choosing the next piece that offers the most immediate benefit.
- The **Greedy Algorithm** is used to solve the **Fractional Knapsack Problem** by sorting the items based on their value-to-weight ratio in non-increasing order and then adding the items to the knapsack one by one until the knapsack is full.

---

## **Algorithm**

- The **Greedy Algorithm** to solve the **Fractional Knapsack Problem** is as follows:

1. **Sort** the items based on their value-to-weight ratio in non-increasing order.
2. If the index is greater than or equal to the number of items or the capacity of the knapsack is less than or equal to 0, return 0.
3. If the weight of the item at the current index is less than or equal to the remaining capacity of the knapsack, add the entire item to the knapsack and update the remaining capacity of the knapsack.
4. If the weight of the item at the current index is greater than the remaining capacity of the knapsack, add a fraction of the item to the knapsack such that the entire capacity of the knapsack is utilized and the remaining capacity of the knapsack is updated to 0.
5. Return the total value of the knapsack.
6. **End**.

---

## **Pseudocode**

- The **Pseudocode** for the **Greedy Algorithm** to solve the **Fractional Knapsack Problem** is as follows:

```cpp
struct Item {
    int value, weight;
};

bool compare(Item item1, Item item2) {
    double ratio1 = (double) item1.value / item1.weight;
    double ratio2 = (double) item2.value / item2.weight;
    return ratio1 > ratio2;
}

double fractionalKnapsack(int capacity, Item items[], int n, int index) {
    sort(items, items + n, compare);
    if (index >= n || capacity <= 0) {
        return 0;
    }

    if (items[index].weight <= capacity) {
        return items[index].value + fractionalKnapsack(capacity - items[index].weight, items, n, index + 1);
    }

    double fraction = (double) capacity / items[index].weight;
    return items[index].value * fraction + fractionalKnapsack(0, items, n, index + 1);
}
```

- The **Pseudocode** sorts the items based on their value-to-weight ratio in non-increasing order and then adds the items to the knapsack one by one until the knapsack is full.
- If the weight of the item is less than or equal to the remaining capacity of the knapsack, the entire item is added to the knapsack and the remaining capacity of the knapsack is updated.
- If the weight of the item is greater than the remaining capacity of the knapsack, a fraction of the item is added to the knapsack such that the entire capacity of the knapsack is utilized and the remaining capacity of the knapsack is updated to 0.
- The total value of the knapsack is then returned.

---

## **Complexity Analysis**

- Best Case Time Complexity: `O(n log n)`
- Average Case Time Complexity: `O(n log n)`
- Worst Case Time Complexity: `O(n log n)`
- Space Complexity: `O(1)`

---

## **Simulation/Visualization**

<p align="center">
    <img src="https://www.geeksforgeeks.org/wp-content/uploads/Fractional-Knapsackexample-min-768x384.png" alt="0/1 Knapsack Problem - Dynamic Programming"/>
</p>

- **Web Based Resources**:
  - [**GeeksforGeeks**](https://www.geeksforgeeks.org/fractional-knapsack-problem/)
  - [**Javatpoint**](https://www.javatpoint.com/fractional-knapsack-problem)
  - [**Tutorialspoint**](https://www.tutorialspoint.com/data_structures_algorithms/fractional_knapsack_problem.htm)

- **Video Resources**:
  - [**3.1 Knapsack Problem - Greedy Method - Abdul Bari**](https://www.youtube.com/watch?v=oTTzNMHM05I)
  - [**Fractional Knapsack Problem | GeeksforGeeks - GeeksforGeeks**](https://www.youtube.com/watch?v=m1p-eWxrt6g)

---
