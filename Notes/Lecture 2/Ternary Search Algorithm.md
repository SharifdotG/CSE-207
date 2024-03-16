# **CSE 207 - Algorithms - Notes - Ternary Search Algorithm**

<p align="center">
    <img src="https://media.geeksforgeeks.org/wp-content/uploads/ternaryS-3.png" alt="Ternary Search Algorithm"/>
</p>

---

## **Introduction**

- **Ternary Search** is a **search algorithm** that finds the position of a target value within a **sorted array**.
- It compares the target value to the two **midpoints** of the array.
- If they are not equal, the two-thirds in which the target cannot lie are eliminated and the search continues on the remaining third, again taking the two midpoints to compare to the target value, and repeating this until the target value is found.
- The **ternary search** algorithm is a **logarithmic** algorithm, which means that the time complexity grows logarithmically with the size of the input data.
- The **ternary search** algorithm is a **divide and conquer** algorithm.
- The **ternary search** algorithm is an **improvement** over the **binary search** algorithm.

---

## **Divide & Conquer in Ternary Search**

- **Divide**: Divide the array into three thirds.
- **Conquer**: Recursively search the target value in the three thirds.
- **Combine**: No need to combine the results.

---

## **Algorithm**

1. If Right element is greater than or equal to Left element,
2. Calculate the two middle elements.
3. If the first middle element is equal to the target element, return the first middle element.
4. If the second middle element is equal to the target element, return the second middle element.
5. If the first middle element is greater than the target element, recursively search the left third of the array.
6. If the second middle element is less than the target element, recursively search the right third of the array.
7. If the first middle element is less than the target element and the second middle element is greater than the target element, recursively search the middle third of the array.
8. If the target element is not found, return -1.

---

## **Pseudocode**

```cpp
int ternarySearch(int array[], int target, int left, int right) {
    if (right >= left) {
        int mid1 = left + (right - left) / 3;
        int mid2 = right - (right - left) / 3;

        if (array[mid1] == target) {
            return mid1;
        }

        if (array[mid2] == target) {
            return mid2;
        }

        if (array[mid1] > target) {
            return ternarySearch(array, target, left, mid1 - 1);
        }

        if (array[mid2] < target) {
            return ternarySearch(array, target, mid2 + 1, right);
        }

        return ternarySearch(array, target, mid1 + 1, mid2 - 1);
    }

    return -1;
}
```

---

## **Simulation/Visualization**

<p align="center">
    <img src="https://media.geeksforgeeks.org/wp-content/uploads/ternaryS-3.png" alt="Ternary Search Algorithm"/>
</p>

- **Web Based Resources**:
  - [GeeksforGeeks](https://www.geeksforgeeks.org/ternary-search/)
  - [CP-Algorithms](https://cp-algorithms.com/num_methods/ternary_search.html)
  - [Educative](https://www.educative.io/answers/what-is-the-ternary-search)

- **Video Resources**:
  - [Ternary Search | Ternary Search with example | Easy explanation of Ternary Search - Code Wagon](https://www.youtube.com/watch?v=WyWL1PBNvb8)
  - [Ternary Search in 4 min (Python) - Quoc Dat Phung](https://www.youtube.com/watch?v=o3HPRpbGlbI)

---

## **Complexity Analysis**

- **Time Complexity**:
  - Best Case: O(1): The target element is found at the first middle element.
  - Average Case: O(log<sub>3</sub>n): The target element is found after a few iterations.
  - Worst Case: O(log<sub>3</sub>n)): The target element is found after a few iterations.
- **Space Complexity**: O(1): The space complexity of the **ternary search** algorithm is **constant**.

---

## **Calculating the Time Complexity Using Master Method**

- **Master Theorem**: T(n) = a * T(n/b) + f(n<sup>d</sup>)
  - If f(n) = O(n<sup>c</sup>), where d < log<sub>b</sub>a, then T(n) = O(n<sup>log<sub>b</sub>a</sup>)
  - If f(n) = O(n<sup>c</sup>), where d = log<sub>b</sub>a, then T(n) = O(n<sup>d</sup> * log n)
  - If f(n) = O(n<sup>c</sup>), where d > log<sub>b</sub>a, then T(n) = O(f(n))
- **Ternary Search**: T(n) = T(n/3) + O(1)
  - a = 1, b = 3, f(n) = O(1)
  - d = 0, log<sub>3</sub>1 = 0
  - d = log<sub>3</sub>1
  - T(n) = O(log<sub>3</sub>n)
  - **Time Complexity**: O(log<sub>3</sub>n)

---
