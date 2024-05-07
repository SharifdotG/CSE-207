# **CSE 207 - Algorithms - Notes - 15-Puzzle Problem**

<p align="center">
    <img src="https://miro.medium.com/v2/resize:fit:600/format:webp/1*Kg5sN-5U3Q7hevW9qhz2rA.gif" alt="N-Queens Problem"/>
</p>

---

## **Introduction**

- **15-Puzzle Problem** is a classic problem in computer science.
- It is a combinatorial problem that involves sliding tiles on a 4x4 grid.
- The goal is to arrange the tiles in numerical order from 1 to 15.
- The problem is to find the minimum number of moves to solve the 15-Puzzle Problem.
- The problem is solved using the **Branch and Bound** technique.
- The problem is a variant of the **N-Queens Problem**.
- It was invented by Sam Loyd in 1878.
- The tiles can be moved in four directions: up, down, left, and right.
- We are given an initial configuration of the 15-Puzzle and we have to reach the goal configuration.

---

## **Cost Function for 15-Puzzle Problem**

- The cost function for the **15-Puzzle Problem** is as follows:
- **C(x)** = **g(x)** + **h(x)**
  - **g(x)** = Number of moves made so far.
  - **h(x)** = Number of misplaced tiles.
  - Whilst there are at least h(x) moves from state x to the goal state, the cost of x is at least h(x).

---

## **Algorithm**

- The **15-Puzzle Problem** is as follows:
- Initialize a priority queue **Q** with the initial state.
- While **Q** is not empty:
  - Dequeue the state with the lowest cost.
  - If the state is the goal state, print the solution.
  - Otherwise, generate all possible states from the current state.
  - Calculate the cost of each state using the cost function.
  - Enqueue the states in the priority queue **Q**.
- If the priority queue **Q** is empty, print "No solution".

---

## **Pseudocode**

- The pseudocode for the **15-Puzzle Problem** is as follows:

```cpp
int solve15Puzzle(int initial[4][4], int goal[4][4]) {
    // Initialize priority queue Q with initial state
    Q.push(initial);

    while (!Q.empty()) {
        // Dequeue state with lowest cost
        state = Q.pop();

        if (state == goal) {
            // Print solution
            return state;
        }

        // Generate all possible states from current state
        for (int i = 0; i < 4; i++) {
            for (int j = 0; j < 4; j++) {
                if (state[i][j] == 0) {
                    // Move empty tile up, down, left, right
                    newState = moveTile(state, i, j, i-1, j);
                    newState = moveTile(state, i, j, i+1, j);
                    newState = moveTile(state, i, j, i, j-1);
                    newState = moveTile(state, i, j, i, j+1);
                }
            }
        }

        // Calculate cost of each state using cost function
        cost = calculateCost(state);

        // Enqueue states in priority queue Q
        Q.push(newState);
    }

    // No solution found
    return "No solution";
}
```

---

## **Complexity Analysis**

- The time complexity of the **15-Puzzle Problem** is **O(b<sup>d</sup>)**.
- **b** = Branching factor = 4 (up, down, left, right).
- **d** = Depth of the state space tree.
- The space complexity of the **15-Puzzle Problem** is **O(b<sup>d</sup>)**.

---

## **Simulation/Visualization**

<p align="center">
    <img src="https://raw.githubusercontent.com/imshubhamsingh/15-puzzle/master/screenshots/game.gif" alt="15-Puzzle Problem"/>
</p>

- **Web Based Resources**:
  - [**GeeksforGeeks**](https://www.geeksforgeeks.org/check-instance-15-puzzle-solvable/)
  - [**CP-Algorithms**](https://cp-algorithms.com/others/15-puzzle.html)

- **Video Resources**:
  - [**Branch and Bound 15 Puzzle Problem Game Tree - Tutorialspoint**](https://www.youtube.com/watch?v=dA7FkYkoTJc)
  - [**Branch and Bound 15 Puzzle Problem - Tutorialspoint**](https://www.youtube.com/watch?v=l6bqjCDK3Kg)

---
