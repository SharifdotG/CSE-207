# **CSE 207 - Algorithms - Notes - Rabin Karp Algorithm**

<p align="center">
    <img src="https://miro.medium.com/v2/resize:fit:1400/1*-NX8U6tAaZlnUQ6svxnllw.gif" alt="0/1 Knapsack Problem"/>
</p>

---

## **Introduction**

- **Rabin-Karp Algorithm** is a string searching algorithm.
- Similar to the **Naive Algorithm**, it is used to find the occurrences of a pattern in a text.
- It even examines each character of the text similar to the **Naive Algorithm**.
- But, it uses a **hash function** to compute the hash value of the pattern and the text.
- If the hash values match, it compares the characters of the pattern and the text.
- It is used in various applications such as search engines, text editors, and bioinformatics.

---

## **Hash Function**

- A **hash function** is a function that converts an input (or 'message') into a fixed-size string of bytes.
- The output is typically a **digest** that is unique to each unique input.
- The **hash function** is used to compute the hash value of the pattern and the text.
- The **hash value** is a numerical value that represents the pattern or the text.
- It is used to compare the pattern and the text. If the hash values match, it compares the characters of the pattern and the text.
- **Rolling Hash** is a type of **hash function** that is used in the **Rabin-Karp Algorithm**.
  - The Rabbin-Karp algorithm uses a rolling hash function to compute the hash value of the pattern and the text.
  - It slides the window of the pattern over the text and computes the hash value of the pattern and the text at each step.
  - While taking into account the hash value of the previous window and the hash value of the current window.

---

## **How Hash Function Works?**

- Consider a simple hash function that assigns each character a unique number. This number is the hash value of the character and it is based on the position of the character in the alphabet.
  - For example, 'A' is assigned the hash value 1, 'B' is assigned the hash value 2, and so on.
- Suppose we have a pattern 'ABC' and a text 'ABCDABCD'.
  - The hash value of the pattern is 1 + 2 + 3 = 6.
  - If we slide the window of the pattern over the text, the hash value of the text at each step is computed.

<p align="center">
    <img src="https://i.makeagif.com/media/3-08-2020/mW0ALq.gif" alt="0/1 Knapsack Problem"/>
</p>

---

## **Algorithm**

- The **Rabin-Karp Algorithm** to find the occurrences of a pattern in a text is as follows:
- **Input**: A text `T` of length `n` and a pattern `P` of length `m`.
- **Output**: The starting indices of the occurrences of the pattern `P` in the text `T`.
- **Steps**:
  1. Compute the hash value of the pattern `P` and the first window of the text `T`.
  2. Slide the window of the pattern over the text and compute the hash value of the pattern and the text at each step.
  3. If the hash values match, compare the characters of the pattern and the text.
  4. If the characters match, check if the pattern is found in the text.
  5. If the pattern is found, store the starting index of the occurrence.
  6. Continue the process until the pattern is found in the text.
  7. Return the starting indices of the occurrences of the pattern in the text.
  8. **End**.

---

## **Pseudocode**

- The **Pseudocode** for the **Rabin-Karp Algorithm** to find the occurrences of a pattern in a text is as follows:

```cpp
int calculateHash(string str, int length) {
    int hashValue = 0;

    for (int i = 0; i < length; i++) {
        hashValue += str[i];
    }

    return hashValue;
}

void RabinKarp(string text, string pattern) {
    int textSize = text.length();
    int patternSize = pattern.length();

    int patternHash = calculateHash(pattern, patternSize);
    int textHash = calculateHash(text, patternSize);

    for (int i = 0; i <= textSize - patternSize; i++) {
        if (patternHash == textHash) {
            bool found = true;

            for (int j = 0; j < patternSize; j++) {
                if (text[i + j] != pattern[j]) {
                    found = false;
                    break;
                }
            }

            if (found) {
                cout << "Pattern found at index " << i << endl;
            }
        }

        if (i < textSize - patternSize) {
            textHash -= text[i];
            textHash += text[i + patternSize];
        }
    }
}
```

---

## **Complexity Analysis**

- **Time Complexity**:
  - Processing the pattern: `O(m)`
  - Best Case: `O(n)`
  - Average Case: `O(n)`
  - Worst Case: `O(n - m + 1) * m + O(m)`
  - The **Rabin-Karp Algorithm** has a linear time complexity in the best and average cases.

- **Space Complexity**: `O(1)`
  - The **Rabin-Karp Algorithm** has a constant space complexity.
  - It only uses a constant amount of space to store the hash values of the pattern and the text.
  - The space complexity does not depend on the size of the input.

---

## **Simulation/Visualization**

<p align="center">
    <img src="https://d18l82el6cdm1i.cloudfront.net/uploads/uIPjisbiCM-bruteforce.gif" alt="0/1 Knapsack Problem - Dynamic Programming"/>
</p>

- **Web Based Resources**:
  - [**GeeksforGeeks**](https://www.geeksforgeeks.org/rabin-karp-algorithm-for-pattern-searching/)
  - [**Programiz**](https://www.programiz.com/dsa/rabin-karp-algorithm)
  - [**Javatpoint**](https://www.javatpoint.com/daa-rabin-karp-algorithm)
  - [**CP-Algorithms**](https://cp-algorithms.com/string/rabin-karp.html)

- **Video Resources**:
  - [**9.2 Rabin-Karp String Matching Algorithm - Abdul Bari**](https://www.youtube.com/watch?v=qQ8vS2btsxI)
  - [**Rabin-Karp Algorithm | Searching for Patterns | GeeksforGeeks - GeeksforGeeks**](https://www.youtube.com/watch?v=oxd_Z1osgCk)

---
