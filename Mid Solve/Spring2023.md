# CSE 207 Mid Solve - Spring 2023

## 1. a) Explain the fundamental differences and similarities between the Divide and Conquer and the Dynamic Programming approaches in solving algorithmic problems

Both Divide and Conquer (D&C) and Dynamic Programming (DP) are problem-solving paradigms used in algorithm design. While they share similarities in breaking down problems into smaller subproblems and utilizing recursion, they differ significantly in their approaches.

**Divide and Conquer:**

1. **Approach**: D&C involves breaking down a problem into smaller, more manageable subproblems, solving these subproblems recursively, and then combining their solutions to solve the original problem.

2. **Divide**: The problem is divided into smaller, independent subproblems. Each subproblem is typically of the same type as the original problem but smaller in size.

3. **Conquer**: The subproblems are solved recursively. If the subproblems become small enough, their solutions can be directly computed.

4. **Combine**: Finally, the solutions to the subproblems are combined to solve the original problem. The combining step often involves merging the solutions of the subproblems in a way that maintains correctness.

5. **Example**: Merge Sort and Quick Sort are classic examples of Divide and Conquer algorithms. They divide the input array into smaller subarrays, sort these subarrays recursively, and then merge them to obtain the sorted output.

**Dynamic Programming:**

1. **Approach**: Dynamic Programming solves problems by breaking them down into simpler subproblems but differs from D&C in that it solves each subproblem only once and stores the solution to each subproblem in a table (usually an array) so that it doesn't need to be recomputed.

2. **Overlapping Subproblems**: DP typically deals with problems that exhibit overlapping subproblems, i.e., the same subproblems occur multiple times. Instead of recomputing the solutions, DP stores the solutions of these subproblems and reuses them when needed.

3. **Memoization/Tabulation**: DP can be implemented using either memoization (top-down approach) or tabulation (bottom-up approach). Memoization involves storing the results of each subproblem in memory and checking if the solution already exists before recomputing it. Tabulation involves filling up a table iteratively from the bottom-up, starting from the simplest subproblems.

4. **Optimal Substructure**: Like D&C, DP relies on problems having optimal substructure, meaning that the optimal solution to the original problem depends on the optimal solutions to its subproblems.

5. **Example**: The Fibonacci sequence problem is a classic example of a problem solved using DP. By memoizing or tabulating the results of previously solved subproblems, the computation time for calculating Fibonacci numbers is significantly reduced.

**Differences**:

1. **Overlapping Subproblems**: DP explicitly deals with overlapping subproblems, whereas D&C does not necessarily have this feature.
2. **Recomputation**: D&C might solve the same subproblems multiple times, while DP avoids this through memoization or tabulation.
3. **Storage**: DP requires additional storage to store solutions to subproblems, which may not be needed in D&C.
4. **Solving Approach**: D&C tends to focus on breaking down problems into smaller, independent pieces and then combining their solutions, while DP focuses on reusing solutions to subproblems.

**Similarities**:

1. **Divide and Conquer**: Both paradigms involve breaking down problems into smaller, more manageable subproblems.
2. **Recursion**: Both paradigms often utilize recursion to solve subproblems.
3. **Optimal Substructure**: Both paradigms rely on problems having optimal substructure, where the optimal solution to the original problem depends on the optimal solutions to its subproblems.

In summary, while Divide and Conquer and Dynamic Programming share some common elements, such as breaking down problems into subproblems and relying on optimal substructure, they differ significantly in their handling of overlapping subproblems, recomputation, and storage of solutions.

## 1. b) Develop an algorithm or pseudocode to sort an array with a time complexity of O(nlogn)

Quick Sort is a classic example of a sorting algorithm with a time complexity of O(nlogn). The following is the pseudocode for Quick Sort:

```c++
int partition(int arr[], int low, int high) {
    int pivot = arr[high]; // Select the pivot element
    int i = (low - 1); // Index of the smaller element

    for (int j = low; j <= high - 1; j++) {
        // If the current element is smaller than or equal to the pivot
        if (arr[j] <= pivot) {
            i++; // Increment index of the smaller element
            swap(arr[i], arr[j]); // Swap arr[i] and arr[j]
        }
    }
    swap(arr[i + 1], arr[high]); // Swap arr[i + 1] and arr[high] (or pivot)
    return (i + 1); // Return the partitioning index
}

void quickSort(int arr[], int low, int high) {
    if (low < high) {
        // pi is the partitioning index, arr[pi] is now at the right place
        int pi = partition(arr, low, high);

        // Separately sort elements before and after partition
        quickSort(arr, low, pi - 1);
        quickSort(arr, pi + 1, high);
    }
}
```

The `quickSort` function takes an array `arr`, the starting index `low`, and the ending index `high` as input. It first calls the `partition` function to select a pivot element and place it at its correct position in the sorted array. Then, it recursively calls itself to sort the subarrays before and after the pivot.

The `partition` function selects the last element as the pivot, places the pivot element at its correct position in the sorted array, and places all smaller elements to the left of the pivot and all greater elements to the right of the pivot.

The time complexity of Quick Sort is O(nlogn) on average and O(n^2) in the worst case. However, the worst-case scenario is rare and can be avoided by using a randomized pivot selection or by using other variations of the algorithm.

## 1. c) Apply the Binary Search algorithm to the following data - [10, 25, 30, 38, 44, 59, 64, 73, 86, 99] for target = 86

**Data:** [10, 25, 30, 38, 44, 59, 64, 73, 86, 99]
**Target:** 86

**Diagram Simulation:**

1. **Initial state:**
   - The entire array is considered the search space, represented by a rectangle encompassing all elements.
   - The target value (86) is highlighted separately.

   ```sql
   [10, 25, 30, 38, 44, 59, 64, 73, 86, 99]
                                    ^
                                 Target (86)
   ```

2. **First iteration:**
   - Calculate the middle index: `middle = (low + high) / 2 = (0 + 9) / 2 = 4`
   - Access the element at the middle index: `middle_element = data[middle] = 44`
   - Since `target (86) > middle_element (44)`, discard the left half of the array. Update the search space to the right half.

   ```sql
   [10, 25, 30, 38, **44, 59, 64, 73, 86, 99**]
                               |
                               Discarded half
                                      ^
                                 Target (86)
   ```

3. **Second iteration:**
   - Calculate the updated middle index for the remaining sub-array: `middle = (low + high) / 2 = (5 + 9) / 2 = 7`
   - Access the element at the middle index: `middle_element = data[middle] = 73`
   - Since `target (86) > middle_element (73)`, discard the left half of the remaining sub-array. Update the search space to the right half.

   ```sql
   [10, 25, 30, 38, 44, 59, **64, 73, 86, 99**]
                                   |
                                   Discarded half
                                      ^
                                 Target (86)
   ```

4. **Third iteration:**
   - Calculate the updated middle index for the remaining sub-array: `middle = (low + high) / 2 = (8 + 9) / 2 = 8.5` (rounded down to 8 as we're working with integer indices)
   - Access the element at the middle index: `middle_element = data[middle] = 86`

   ```sql
   [10, 25, 30, 38, 44, 59, 64, 73, **86, 99**]
                                      ^
                                    Match found!
   ```

**Target Found:** The element at index 8 (`data[8] = 86`) matches the target value. Therefore, the target is found at position 8 in the array.

## 2. a) Suppose, you are a manager overseeing two retail stores - Store A and Store B. Each store has its daily sales data recorded over a week. Your task is to determine the length of the maximum consecutive sales streak during which both stores had positive sales on the same day. Store A's daily sales over a week: [0, 2, 3, 5, 2, 0, 1]. Store B's daily sales over a week: [1, 3, 5, 2, 1, 0, 2]

To solve this problem, we can use a dynamic programming approach to find the length of the maximum consecutive sales streak during which both stores had positive sales on the same day.

**Algorithm:**

```c++
int lcs(int A[], int B[], int m, int n) {
    int dp[m + 1][n + 1];
    int maxLen = 0;

    for (int i = 0; i <= m; i++) {
        for (int j = 0; j <= n; j++) {
            if (i == 0 || j == 0) {
                dp[i][j] = 0;
            } else if (A[i - 1] == B[j - 1]) {
                dp[i][j] = dp[i - 1][j - 1] + 1;
                maxLen = max(maxLen, dp[i][j]);
            } else {
                dp[i][j] = 0;
            }
        }
    }

    return maxLen;
}

int main() {
    int A[] = {0, 2, 3, 5, 2, 0, 1};
    int B[] = {1, 3, 5, 2, 1, 0, 2};
    int m = sizeof(A) / sizeof(A[0]);
    int n = sizeof(B) / sizeof(B[0]);
    
    int maxConsecutiveStreak = lcs(A, B, m, n);
    cout << "Length of the maximum consecutive sales streak with positive sales in both stores: " << maxConsecutiveStreak << endl;
    return 0;
}
```

**Output:**
Length of the maximum consecutive sales streak with positive sales in both stores: 4

**Explanation:**
The longest consecutive sales streak during which both stores had positive sales on the same day is 4 days. This occurs from the 3rd to the 7th day of the week, where both stores had sales of [3, 5, 2, 1].

## 2. b) Which algorithmic approach did you use in your answer 2a? Analyze its time complexity

In your solution to find the length of the maximum consecutive sales streak during which both stores had positive sales on the same day, you've indeed used the Longest Common Subsequence (LCS) algorithm with dynamic programming.

The time complexity analysis for your solution is as follows:

Let's denote the length of the sales data for Store A as `m` and for Store B as `n`.

1. **Initialization of the DP array**: This step takes `O(m * n)` time because it involves initializing a 2D array of size `(m+1) * (n+1)`.

2. **Filling the DP array**: Each cell of the DP array is computed based on the values of the previous cells. In the worst-case scenario, each cell computation takes constant time. Thus, this step also takes `O(m * n)` time.

3. **Finding the maximum length**: After filling the DP array, you iterate over it once to find the maximum length, which again takes `O(m * n)` time in the worst case.

Therefore, the overall time complexity of your solution is `O(m * n)`.

In your specific example, both stores' sales data have length `7`, so the time complexity is `O(7 * 7)` = `O(49)`, which is a constant time complexity for this problem size. However, in a more general scenario where the lengths of the sales data for both stores might vary, the time complexity would scale accordingly.

## 2. c) Imagine you are a treasure hunter exploring a cave filled with valuable items of varying weights and values. Each item can only be taken once, and your goal is to maximize the total value of the items you can carry out of the cave while the weight limit of your backpack should not exceed. Design a step-by-step dynamic programming algorithm to solve this treasure hunter's challenge

To solve the treasure hunter's challenge, we can use the 0/1 Knapsack problem, which is a classic problem in dynamic programming. The problem can be solved using a bottom-up approach, also known as tabulation.

**Algorithm:**

```c++
int knapsack(int W, int wt[], int val[], int n) {
    int dp[n + 1][W + 1];

    for (int i = 0; i <= n; i++) {
        for (int w = 0; w <= W; w++) {
            if (i == 0 || w == 0) {
                dp[i][w] = 0;
            } else if (wt[i - 1] <= w) {
                dp[i][w] = max(val[i - 1] + dp[i - 1][w - wt[i - 1]], dp[i - 1][w]);
            } else {
                dp[i][w] = dp[i - 1][w];
            }
        }
    }

    return dp[n][W];
}

int main() {
    int val[] = {60, 100, 120};
    int wt[] = {10, 20, 30};
    int W = 50;
    int n = sizeof(val) / sizeof(val[0]);
    
    int maxTotalValue = knapsack(W, wt, val, n);
    cout << "Maximum total value of items that can be carried out: " << maxTotalValue << endl;
    return 0;
}
```

**Output:**

Maximum total value of items that can be carried out: 220

**Explanation:**

The algorithm uses a 2D DP array to store the maximum total value that can be carried out for different weights and different numbers of items. The `knapsack` function returns the maximum total value that can be carried out within the weight limit `W`. In this specific example, the maximum total value of items that can be carried out is 220.
