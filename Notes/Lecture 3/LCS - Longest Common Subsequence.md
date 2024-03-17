# **CSE 207 - Algorithms - Notes - Longest Common Subsequence**

<p align="center">
    <img src="https://media.geeksforgeeks.org/wp-content/uploads/20230711111122/LCS-1.png" alt="Longest Common Subsequence"/>
</p>

---

## **Introduction**

- **Longest Common Subsequence (LCS)** is a problem to find the longest subsequence that is present in given two sequences.
- It is a classic computer science problem and has applications in **Bioinformatics**.
- It is solved using **Dynamic Programming**.
- **Longest Common Subsequence (LCS)** is a subsequence that is common to both the sequences. It is not necessary to be continuous. It can be discontinuous.

---

**What is a Subsequence?**

- A subsequence is a sequence that can be derived from another sequence by deleting some or no elements without changing the order of the remaining elements.
- For example, `ACE` is a subsequence of `ABCDE` but not a subsequence of `AED`.
- The empty sequence is a subsequence of any sequence.
- Any sequence is a subsequence of itself.
- The length of the longest common subsequence is the maximum length of a subsequence that is common to both the sequences.

---

## **Subsequence vs Substring**

| Subsequence | Substring |
| --- | --- |
| A subsequence is a sequence that can be derived from another sequence by deleting some or no elements without changing the order of the remaining elements. | A substring is a contiguous sequence of characters within a string. |
| A subsequence is not necessary to be continuous. It can be discontinuous. | A substring is continuous. |
| The empty sequence is a subsequence of any sequence. | The empty string is a substring of any string. |
| Any sequence is a subsequence of itself. | Any string is a substring of itself. |
| The length of the longest common subsequence is the maximum length of a subsequence that is common to both the sequences. | The length of the longest common substring is the maximum length of a substring that is common to both the strings. |
| Example: `ACE` is a subsequence of `ABCDE` but not a subsequence of `AED`. | Example: `ABC` is a substring of `ABCDE` but not a substring of `AED`. |

---

## **Apllications of Longest Common Subsequence (LCS)**

- **Bioinformatics**: It is used to find the similarity between the DNA sequences of two species.
- **Version Control Systems**: It is used to find the difference between two versions of a file.
- **Data Comparison**: It is used to find the difference between two data files.
- **Speech Recognition**: It is used to find the similarity between two voice signals.
- **Natural Language Processing**: It is used to find the similarity between two texts.
- **Plagiarism Detection**: It is used to find the similarity between two documents.
- **Linguistics**: It is used to find the similarity between two languages.

---

## **Longest Common Subsequence (LCS) - Recursive Approach**

- The **Recursive Approach** to solve the **Longest Common Subsequence (LCS)** problem is to use **Recursion**.
- It has an **exponential time complexity**.
- It has a **time complexity** of `O(2^n)`.
- It has a **space complexity** of `O(n)`.
- The **Recursive Approach** is not efficient.
- The **Recursive Approach** is not recommended for large inputs.

```cpp
int lcs(string s1, string s2, int m, int n) {
    if (m == 0 || n == 0) {
        return 0;
    } else if (s1[m - 1] == s2[n - 1]) {
        return 1 + lcs(s1, s2, m - 1, n - 1);
    } else {
        return max(lcs(s1, s2, m, n - 1), lcs(s1, s2, m - 1, n));
    }
}
```
- Here, `lcs(s1, s2, m, n)` represents the length of the longest common subsequence of the strings `s1` and `s2` of lengths `m` and `n` respectively.
- The base case of the recursion is when `m` is `0` or `n` is `0`.

---

## **Longest Common Subsequence (LCS) - Dynamic Programming Approach**

- The **Dynamic Programming Approach** to solve the **Longest Common Subsequence (LCS)** problem is to use **Dynamic Programming**.
- It has a **time complexity** of `O(m*n)`.
- It has a **space complexity** of `O(m*n)`.
- The **Dynamic Programming Approach** is efficient.
- The **Dynamic Programming Approach** is recommended for large inputs.

---

## **Algorithm**

1. Create a 2D array `dp[][]` of size `(m + 1) x (n + 1)`.
2. Initialize the first row and the first column of the array `dp[][]` with `0`.
3. For each element `i` from `1` to `m` and each element `j` from `1` to `n`, calculate the value of `dp[i][j]` as:
   - `dp[i][j] = 1 + dp[i - 1][j - 1]` if `s1[i - 1] == s2[j - 1]`
   - `dp[i][j] = max(dp[i - 1][j], dp[i][j - 1])` if `s1[i - 1] != s2[j - 1]`
   - Here, `dp[i][j]` represents the length of the longest common subsequence of the strings `s1` and `s2` of lengths `i` and `j` respectively.
   - The value of `dp[m][n]` is the length of the longest common subsequence of the strings `s1` and `s2`.
4. The base case of the recursion is when `i` is `0` or `j` is `0`.

---

## **Pseudocode**

```cpp
int lcs(string s1, string s2, int m, int n) {
    int dp[m + 1][n + 1];
    
    for (int i = 0; i <= m; i++) {
        for (int j = 0; j <= n; j++) {
            if (i == 0 || j == 0) {
                dp[i][j] = 0;
            } else if (s1[i - 1] == s2[j - 1]) {
                dp[i][j] = 1 + dp[i - 1][j - 1];
            } else {
                dp[i][j] = max(dp[i - 1][j], dp[i][j - 1]);
            }
        }
    }

    return dp[m][n];
}
```

- Here, `dp[i][j]` represents the length of the longest common subsequence of the strings `s1` and `s2` of lengths `i` and `j` respectively.
- The base case of the recursion is when `i` is `0` or `j` is `0`.
- The value of `dp[m][n]` is the length of the longest common subsequence of the strings `s1` and `s2`.

---

## **Tabulation**

- Suppose the strings are `AGGTAB` and `GXTXAYB`.
- The table `dp[][]` is as follows:

  |   | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
  | --- | --- | --- | --- | --- | --- | --- | --- | --- |
  | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
  | 1 | 0 | 0 | 0 | 0 | 1 | 1 | 1 | 1 |
  | 2 | 0 | 0 | 1 | 1 | 1 | 1 | 1 | 1 |
  | 3 | 0 | 0 | 1 | 1 | 1 | 2 | 2 | 2 |
  | 4 | 0 | 1 | 1 | 1 | 1 | 2 | 2 | 2 |
  | 5 | 0 | 1 | 1 | 2 | 2 | 2 | 2 | 3 |
  | 6 | 0 | 1 | 1 | 2 | 2 | 3 | 3 | 3 |

- The value of `dp[6][7]` is `3`.
- The length of the longest common subsequence is `3`.
- The longest common subsequence is `GTAB`.

---

## **Recursive Approach vs Dynamic Programming Approach**

| Recursive Approach | Dynamic Programming Approach |
| --- | --- |
| The **Recursive Approach** to solve the **Longest Common Subsequence (LCS)** problem is to use **Recursion**. | The **Dynamic Programming Approach** to solve the **Longest Common Subsequence (LCS)** problem is to use **Dynamic Programming**. |
| It has an **exponential time complexity**. | It has a **time complexity** of `O(m*n)`. |
| It has a **space complexity** of `O(n)`. | It has a **space complexity** of `O(m*n)`. |
| The **Recursive Approach** is not efficient. | The **Dynamic Programming Approach** is efficient. |
| The **Recursive Approach** is not recommended for large inputs. | The **Dynamic Programming Approach** is recommended for large inputs. |

---

## **Complexity Analysis**

- The **Recursive Approach** has an **exponential time complexity** of `O(2^n)`.
- The **Dynamic Programming Approach** has a **time complexity** of `O(m*n)`.
- The **Dynamic Programming Approach** has a **space complexity** of `O(m*n)`.
- The **Dynamic Programming Approach** is efficient.

---

## **Simulation/Visualization**

<p align="center">
    <img src="https://gabrielghe.github.io/assets/themes/images/2016-01-04-longest-common-subsequence3.gif" alt="Longest Common Subsequence"/>
</p>

- **Web Based Resources**:
  - [**GeeksforGeeks**](https://www.geeksforgeeks.org/longest-common-subsequence-dp-4/)
  - [**Programiz**](https://www.programiz.com/dsa/longest-common-subsequence)
  - [**Javatpoint**](https://www.javatpoint.com/longest-common-subsequence)

- **Video Resources**:
  - [**4.9 Longest Common Subsequence (LCS) - Recursion and Dynamic Programming - Abdul Bari**](https://www.youtube.com/watch?v=sSno9rV8Rhg)
  - [**Dynamic Programming | Set 4 (Longest Common Subsequence) | GeeksforGeeks - GeeksforGeeks**](https://www.youtube.com/watch?v=HgUOWB0StNE)
  - [**Longest Common Subsequence - Tushar Roy - Coding Made Simple**](https://www.youtube.com/watch?v=NnD96abizww)

---
