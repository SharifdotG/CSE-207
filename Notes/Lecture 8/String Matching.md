# **CSE 207 - Algorithms - Notes - String Matching**

<p align="center">
    <img src="https://miro.medium.com/v2/0*GJZCKNeMbyKAbrdP.gif" alt="0/1 Knapsack Problem"/>
</p>

---

## **Introduction**

- **String Matching** is a problem in computer science.
- It is the problem of finding all the occurrences of a pattern in a text.
- It is also known as the **Substring Matching Problem** and **Pattern Matching Problem**.
- It is used in various applications such as search engines, text editors, and bioinformatics.
- The **Naive Algorithm** is a simple and straightforward algorithm to solve the **String Matching Problem**.
- The **Naive Algorithm** is used to solve the **String Matching Problem** by comparing the pattern with the text character by character.

---

## **String Matching - By Definition**

1. Text T[1..n]: A string of length n.
2. Pattern P[1..m]: A string of length m where m ≤ n.
3. The elements of P and T are characters from a finite alphabet Σ.
   - For example, Σ = {0, 1} or Σ = {a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z}.
4. The **String Matching Problem** is to find all occurrences of P in T.
5. Given strings T (text) and P (pattern), the **String Matching Problem** is to find all positions i such that T[i..i+m-1] = P[1..m].

## **The Shift**

- The **Shift** is the number of positions the pattern is shifted to the right.
- The **Shift** is used to compare the pattern with the text character by character.
- It is used in Text Mining, Data Mining, and Information Retrieval.
- Search engines use the **Shift** to find the occurrences of a pattern in a text.

---

## **String Matching Algorithms**

1. **Naive Algorithm**
2. **Rabin-Karp Algorithm**
3. **Knuth-Morris-Pratt Algorithm**
4. **Boyer-Moore Algorithm**
5. **Aho-Corasick Algorithm**
6. **Suffix Tree Algorithm**

---

## **Burth Force Algorithm (Native Algorithm)**

- The **Naive Algorithm** is a simple and straightforward algorithm to solve the **String Matching Problem**.
- The Algorithm goes as follows:
  1. For each position i in the text T, compare the pattern P with the text T starting at position i.
  2. If the pattern P matches the text T starting at position i, return the position i.
  3. If the pattern P does not match the text T starting at position i, continue to the next position in the text T.
  4. Return -1 if the pattern P is not found in the text T.
  5. **End**.

---

## **Pseudocode**

- The **Pseudocode** for the **Naive Algorithm** to solve the **String Matching Problem** is as follows:

```cpp
vector<int> naiveStringMatching(string text, string pattern) {
    vector<int> positions;
    int n = text.length();
    int m = pattern.length();

    for (int i = 0; i <= n - m; i++) {
        int j;
        for (j = 0; j < m; j++) {
            if (text[i + j] != pattern[j]) {
                break;
            }
        }

        if (j == m) {
            positions.push_back(i);
        }
    }

    return positions;
}
```

- The **Pseudocode** compares the pattern P with the text T character by character.
- If the pattern P matches the text T starting at position i, the position i is added to the list of positions.
- The list of positions is then returned.
- The **Naive Algorithm** is used to find all occurrences of the pattern P in the text T.

---

## **Complexity Analysis**

- The **Time Complexity** of the **Naive Algorithm** is O((n - m + 1) * m) where n is the length of the text T and m is the length of the pattern P.
- The **Space Complexity** of the **Naive Algorithm** is O(1).
- The **Naive Algorithm** is simple and easy to implement but is not efficient for large texts and patterns.

---
