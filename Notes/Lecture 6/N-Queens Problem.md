# **CSE 207 - Algorithms - Notes - N-Queens Problem**

<p align="center">
    <img src="https://i.makeagif.com/media/11-20-2016/yzWFXo.gif" alt="N-Queens Problem"/>
</p>

---

## **Introduction**

- **N-Queens Problem** is a classic problem in computer science.
- It is a combinatorial problem that involves placing N queens on an N x N chessboard.
- The goal is to place the queens in such a way that no two queens attack each other.
- A queen can attack another queen if they are in the same row, column, or diagonal.
- The problem is to find all possible solutions to the N-Queens Problem.
- The problem is solved using the **Backtracking** technique.

---

## **Algorithm**

- The **N-Queens Problem** is as follows:
- Start from the first row and place a queen in the first column.
- Move to the next row and place a queen in the next column.
- Continue placing queens in the next rows and columns.
- If a queen can be placed in a row and column, place it.
- If a queen cannot be placed in a row and column, backtrack and try another column.
- Continue placing queens until all queens are placed.
- If all queens are placed, print the solution.
- If no solution is found, backtrack and try another column.
- Continue backtracking until all possible solutions are found.
- The algorithm is implemented using the **Backtracking** technique.
- The algorithm explores all possible solutions to the N-Queens Problem.

---

## **Pseudocode**

- The pseudocode for the **N-Queens Problem** is as follows:

```cpp
bool isSafe(int board[10][10], int row, int column, int n) {
    for (int i = 0; i < row; i++) {
        if (board[i][column] == 1) {
            return false;
        }
    }

    for (int i = row, j = column; i >= 0 && j >= 0; i--, j--) {
        if (board[i][j] == 1) {
            return false;
        }
    }

    for (int i = row, j = column; i >= 0 && j < n; i--, j++) {
        if (board[i][j] == 1) {
            return false;
        }
    }

    return true;
}

bool solveNQueens(int board[10][10], int row, int n) {
    if (row == n) {
        return true;
    }

    for (int column = 0; column < n; column++) {
        if (isSafe(board, row, column, n)) {
            board[row][column] = 1;

            if (solveNQueens(board, row + 1, n)) {
                return true;
            }
            
            board[row][column] = 0;
        }
    }

    return false;
}
```

---

## **Complexity Analysis**

- The **N-Queens Problem** has a time complexity of O(N!).
- The **N-Queens Problem** has a space complexity of O(N^2).
- The 27x27 board has 2,353,852,703,443,315,840,000 possible solutions.

---

## **Simulation/Visualization**

<p align="center">
    <img src="https://camo.githubusercontent.com/2bc286557548b178b2cfd33fc5d45f86a598c808445e7dc23d67b647811c2fdb/687474703a2f2f692e696d6775722e636f6d2f4e4c41464949742e676966" alt="N-Queens Problem"/>
</p>

- **Web Based Resources**:
  - [**GeeksforGeeks**](https://www.geeksforgeeks.org/n-queen-problem-backtracking-3/)
  - [**Tutorialspoint**](https://www.tutorialspoint.com/data_structures_algorithms/n_queen_problem.htm)
  - [**Javatpoint**](https://www.javatpoint.com/n-queens-problems)

- **Video Resources**:
  - [**6.1 N Queens Problem using Backtracking - Abdul Bari**](https://www.youtube.com/watch?v=xFv_Hl4B83A)
  - [**N-Queens - Backtracking - Leetcode 51 - Python - NeetCode**](https://www.youtube.com/watch?v=Ph95IHmRp5M)
  - [**N Queen Problem | Backtracking | GeeksforGeeks - GeeksforGeeks**](https://www.youtube.com/watch?v=0DeznFqrgAI)

---
