# CSE 207 Final Solve - Spring 2023

## 1. a) You are a computer scientist working on a project to optimize the packing of items into containers for shipping. Each item has a weight and a value, and your goal is to determine the optimal combination of items to maximize the total value while staying within the weight capacity of the containers. Design a step-by-step dynamic programming algorithm/pseudocode to solve this optimization problem

The problem can be solved using the 0/1 knapsack algorithm. The pseudocode is as follows:

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

## 1. b) What are the key differences between the dynamic programming algorithm and the greedy approach? Why would you choose the above algorithm over the greedy algorithm?

**Key Differences Between Dynamic Programming (DP) and Greedy Approach:**

1. **Decision Making:** DP Considers all possible combinations and makes decisions based on previously computed optimal solutions. Meanwhile, Greedy makes decisions based on the current best choice without considering future consequences.
2. **Optimality:** DP guarantees finding the optimal solution by exploring all possibilities and using previously solved subproblems. But Greedy does not guarantee the optimal solution in all cases, as it might overlook combinations that could lead to a better solution.
3. **Complexity:** DP ypically has a higher time complexity (O(nW) for the Knapsack problem, where n is the number of items and W is the capacity) but ensures optimal results. While Greedy often has a lower time complexity (O(n log n) for sorting plus O(n) for selection) but can lead to suboptimal solutions.

**Reasons to Choose DP Over Greedy:**

1. **Optimality:** DP ensures finding the optimal combination of items to maximize the value within the weight limit, which the greedy approach cannot guarantee due to its local optimization nature.
2. **Flexibility:** DP can handle more complex constraints and scenarios where greedy algorithms might fail to provide the best solution.
3. **Correctness:** For the 0/1 Knapsack problem, where items cannot be fractionally divided, DP is the correct approach as it fully considers the constraints and relationships between items. The greedy approach might work well for fractional knapsack problems but fails to ensure optimality in the 0/1 scenario.

## 2. a) You are given a set of jobs, each having a specific deadline and a corresponding profit if completed within the deadline. Each job takes one unit of time to complete. Create a schedule to maximize the total profit by completing jobs within their respective deadlines using the Greedy approach

| Job ID   | J1  | J2 | J3 | J4  | J5 |
|----------|-----|----|----|-----|----|
| Deadline | 2   | 1  | 2  | 1   | 3  |
| Profit   | 100 | 50 | 10 | 200 | 30 |

Sorting the profits in descending order, we get:

| Job ID   | J4  | J1 | J2 | J5  | J3 |
|----------|-----|----|----|-----|----|
| Deadline | 1   | 2  | 1  | 3   | 2  |
| Profit   | 200 | 100| 50 | 30  | 10 |

**Max Deadline:** **3**
**Max Profit:** **0**

**1st Iteration (Job ID J4):**

| J4 | - | - |
|----|---|---|

0----1----2----3

As Job ID J4 has a deadline of 1, it can be scheduled at time 0 -> 1.

**Max Profit:** **200**

**2nd Iteration (Job ID J1):**

| J4 | J1 | - |
|----|----|---|

0-----1-----2----3

As Job ID J1 has a deadline of 2, it can be scheduled at time 1 -> 2.

**Max Profit:** **200 + 100 = 300**

**3rd Iteration (Job ID J2):**

| J4 | J1 | - |
|----|----|---|

0-----1-----2----3

As Job ID J2 has a deadline of 1, it can't be scheduled at time 0 -> 1. As that slot is already taken by Job ID J4.

**Max Profit:** **300**

**4th Iteration (Job ID J5):**

| J4 | J1 | J5 |
|----|----|----|

0-----1-----2-----3

As Job ID J5 has a deadline of 3, it can be scheduled at time 2 -> 3.

**Max Profit:** **300 + 30 = 330**

**5th Iteration (Job ID J3):**

| J4 | J1 | J5 |
|----|----|----|

0-----1-----2-----3

As Job ID J3 has a deadline of 2, it can't be scheduled at time 1 -> 2. As that slot is already taken by Job ID J1.

As the **simulation ends**, the **job sequence to maximize profit** is **J4, J1, J5** with a **max profit** of **330**.

## 2. b) Design the algorithm/pseudocode for the above problem

The algorithm for the above problem can be designed as follows:

1. Sort the jobs in descending order of their profits.
2. Initialize an empty schedule and an array to keep track of the slots.
3. Iterate through the jobs and for each job, find the latest slot available before the deadline and assign the job to that slot.
4. Calculate the total profit earned by scheduling the jobs.
5. Return the total profit earned.

## 3. a)

<img src="https://scontent.fdac24-2.fna.fbcdn.net/v/t1.15752-9/440893316_1086213292470877_6770912758542901618_n.png?_nc_cat=111&ccb=1-7&_nc_sid=5f2048&_nc_eui2=AeEVgpfi-9wxDzFH6mZ6TY6sJVzBcQgjzpclXMFxCCPOlyvRBGD0C2Vq2vS6OxcFQ24lR7lH0JwQ15Cw3Wjmujxy&_nc_ohc=ucyryZsTMgcQ7kNvgGchPFX&_nc_ht=scontent.fdac24-2.fna&oh=03_Q7cD1QFc3GjYTcmFUuudSl866vC6ItNhaLddPdI6SPlqLG4Rcw&oe=66701F31" alt="Graph">

**Solution:**

<img src="https://images2.imgbox.com/6a/5e/AA6akI3L_o.jpg" alt="Graph">
<img src="https://images2.imgbox.com/cf/d7/eY4v0amp_o.jpg" alt="Graph">
<img src="https://images2.imgbox.com/93/05/XXK1bgMk_o.jpg" alt="Graph">

## 3. b) You have an NxN chessboard and the goal is to place N Queens on the board so that no two Queens threaten each other. Develop the backtracking algorithm to find a solution for an NxN chessboard

The backtracking algorithm to solve the N-Queens problem can be implemented as follows:

1. Start from the first row and place a queen in the first column.
2. Move to the next row and place a queen in the next column.
3. Continue placing queens in the next rows and columns.
4. If a queen can be placed in a row and column, place it.
5. If a queen cannot be placed in a row and column, backtrack and try another column.
6. Continue placing queens until all queens are placed.
7. If all queens are placed, print the solution.
8. If no solution is found, backtrack and try another column.
9. Continue backtracking until all possible solutions are found.

## 4. a)

<img src="https://scontent.fdac24-3.fna.fbcdn.net/v/t1.15752-9/441057153_1019884302892353_5869352813757415151_n.png?_nc_cat=106&ccb=1-7&_nc_sid=5f2048&_nc_eui2=AeGwjmKwLp_jq9xdhOPMhcNOlWOYxiUFu9SVY5jGJQW71E-BsgauMmpzgg0y9j-CkhHhh3xW7p9Z8oys7fgnpwPQ&_nc_ohc=0oosu5AeKboQ7kNvgHq3OUA&_nc_ht=scontent.fdac24-3.fna&oh=03_Q7cD1QGYASeiP0J-LH1X7b11ejDekWWcikGAV8eQv6ud03fomw&oe=6670252B" alt="Graph">

**Solution:**

<img src="https://images2.imgbox.com/37/23/FRahJbM6_o.jpg" alt="Graph">
<img src="https://images2.imgbox.com/0a/d4/j7TQDinM_o.jpg" alt="Graph">
<img src="https://images2.imgbox.com/04/d6/NVSvRlU1_o.jpg" alt="Graph">
<img src="https://images2.imgbox.com/bd/c0/6MPP1OP1_o.jpg" alt="Graph">

## 4. b) You are preparing for a road trip across Bangladesh with a network of cities connected by highways. Each highway has a distance associated with it. Write an algorithm to find the shortest path from your city to all other cities

The algorithm to find the shortest path from a source city to all other cities in a network of cities connected by highways can be implemented using Dijkstra's algorithm:

1. Initialize a distance array to store the shortest distance from the source city to all other cities.
2. Initialize a priority queue to store the cities to be visited based on their distances.
3. Initialize the distance of the source city to itself as 0 and all other distances as infinity.
4. Add the source city to the priority queue.
5. While the priority queue is not empty, do the following:
   - Extract the city with the minimum distance from the priority queue.
   - Update the distances of the neighboring cities based on the current city's distance and the highway distances.
   - Add the neighboring cities to the priority queue if their distances are updated.
   - Repeat the process until all cities are visited.
6. Return the distance array containing the shortest distances from the source city to all other cities.

## 4 OR a)

<img src="https://scontent.fdac24-5.fna.fbcdn.net/v/t1.15752-9/441059186_3717046148617134_256528073936047214_n.png?_nc_cat=101&ccb=1-7&_nc_sid=5f2048&_nc_eui2=AeGVj3a3inOpKk2-ZF6-bF535TdRv8BhCjTlN1G_wGEKNHg69S3YgecR_aMGMWgQKefMFrY1lKjCTx6wojEYamXu&_nc_ohc=kGt_lYViBngQ7kNvgFjFiyw&_nc_ht=scontent.fdac24-5.fna&oh=03_Q7cD1QGA3FqgGkzrOIlKCRPKUw2wxhDMbdh6Ng0TBjzba2PXBw&oe=66700029" alt="Graph">

**Solution:**

<img src="https://images2.imgbox.com/32/e6/JfSzuLgj_o.jpg" alt="Graph">
<img src="https://images2.imgbox.com/b8/29/yeLrEe6W_o.jpg" alt="Graph">
<img src="https://images2.imgbox.com/f0/63/yCzDSuii_o.jpg" alt="Graph">
<img src="https://images2.imgbox.com/44/2c/Bs1a7k26_o.jpg" alt="Graph">

## 4 OR b) Write a detailed algorithm for finding a Minimum Spanning Tree (MST) in a weighted, connected graph. Include the key steps and necessary explanations for your algorithm

The algorithm for finding a Minimum Spanning Tree (MST) in a weighted, connected graph can be implemented using Prim's algorithm:

1. Start from a random vertex in the graph and add it to the Minimum Spanning Tree.
2. Reapeat the following steps until all the vertices are part of the Minimum Spanning Tree:
   - Find the edge with the minimum weight among the edges connected to the vertices in the Minimum Spanning Tree.
   - If the edge connects a vertex that is not part of the Minimum Spanning Tree, add the edge and the vertex to the Minimum Spanning Tree.
3. Return the Minimum Spanning Tree.

## 5. a)

<img src="https://scontent.fdac24-1.fna.fbcdn.net/v/t1.15752-9/436723566_461961189654581_3895085060744385569_n.png?_nc_cat=100&ccb=1-7&_nc_sid=5f2048&_nc_eui2=AeE0uze_kmaHjpZk3-ZfVjgmmP4fsRMBr_eY_h-xEwGv9xJnH6AG-Zmtf7DXA6AzxOudzxFowAnZapWzHtMAazjh&_nc_ohc=nPiIhV8W9hYQ7kNvgF-2n-i&_nc_ht=scontent.fdac24-1.fna&oh=03_Q7cD1QEDjcw54sMv7eodhsmaZB5vF47JNYXz6rYHzKGT9nl0Hg&oe=667023DD" alt="Graph">

**Solution:**

<img src="https://images2.imgbox.com/41/43/b0reMfqY_o.jpg" alt="Graph">
<img src="https://images2.imgbox.com/70/0b/I0ZVZXBx_o.jpg" alt="Graph">
<img src="https://images2.imgbox.com/dc/be/8JGBwQoP_o.jpg" alt="Graph">
<img src="https://images2.imgbox.com/c4/1c/xOnRvQTV_o.jpg" alt="Graph">

## 5. b) Analyze the time complexity of Rabins-Karp Algorithm

The Rabin-Karp algorithm is used for string searching and pattern matching. The time complexity of the Rabin-Karp algorithm is O(n) in the average case, where n is the length of the text. However, in the worst case, the time complexity can be O(n - m + 1) * m + O(m), where m is the length of the pattern.

**Analysis:**

1. **Preprocessing:** The Rabin-Karp algorithm preprocesses the pattern and text to calculate the hash values of the pattern and the initial window of the text. This preprocessing step takes O(m) time.
2. **Sliding Window:** The algorithm slides the window over the text and compares the hash values of the pattern and the window. If the hash values match, it performs a character-by-character comparison. The sliding window operation takes O(n - m + 1) time.
3. **Hash Function:** The hash function used in the Rabin-Karp algorithm is efficient and can be computed in O(1) time.
4. **Character Comparison:** In the worst case, if the hash values match, the algorithm performs a character-by-character comparison, which takes O(m) time.
5. **Overall Time Complexity:** The overall time complexity of the Rabin-Karp algorithm is O(n - m + 1) * m + O(m) in the worst case. However, in the average case, the time complexity is O(n).
