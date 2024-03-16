# **CSE 207 - Algorithms - Notes - Binary Search Algorithm**

<p align="center">
    <img src="https://upload.wikimedia.org/wikipedia/commons/9/9c/Optimal-binary-search-tree-from-sorted-array.gif" alt="Binary Search Algorithm"/>
</p>

---

## **Introduction**

- **Binary Search** is a **search algorithm** that finds the position of a target value within a **sorted array**.
- It compares the target value to the **middle element** of the array.
- If they are not equal, the half in which the target cannot lie is eliminated and the search continues on the remaining half, again taking the middle element to compare to the target value, and repeating this until the target value is found.
- The **binary search** algorithm is a **logarithmic** algorithm, which means that the time complexity grows logarithmically with the size of the input data.
- The **binary search** algorithm is a **divide and conquer** algorithm.

---

## **Divide & Conquer in Binary Search**

- **Divide**: Divide the array into two halves.
- **Conquer**: Recursively search the target value in the two halves.
- **Combine**: No need to combine the results.

---

## **Algorithm**

1. If Right element is greater than or equal to Left element,
2. Calculate the middle element.
3. If the middle element is equal to the target element, return the middle element.
4. If the middle element is greater than the target element, recursively search the left half of the array.
5. If the middle element is less than the target element, recursively search the right half of the array.
6. If the target element is not found, return -1.

---

## **Pseudocode**

```cpp
int binarySearch(int array[], int target, int left, int right) {
    if (right >= left) {
        int middle = left + (right - left) / 2;

        if (array[middle] == target) {
            return middle;
        }

        if (array[middle] > target) {
            return binarySearch(array, target, left, middle - 1);
        }

        return binarySearch(array, target, middle + 1, right);
    }

    return -1;
}
```

---

## **Simulation/Visualization**

<p align="center">
    <img src="https://upload.wikimedia.org/wikipedia/commons/c/c1/Binary-search-work.gif" alt="Binary Search Algorithm"/>
</p>

- **Web Based Resources**:
  - [**GeeksforGeeks**](https://www.geeksforgeeks.org/binary-search/)
  - [**Javatpoint**](https://www.javatpoint.com/binary-search)
  - [**Programiz**](https://www.programiz.com/dsa/binary-search)

- **Video Resources**:
  - [**Binary search in 4 minutes - Michael Sambol**](https://www.youtube.com/watch?v=fDKIpRe8GW4)
  - [**Binary Search Algorithm in 100 Seconds - Fireship**](https://www.youtube.com/watch?v=MFhxShGxHWc)
  - [**2.6.2 Binary Search Recursive Method - Abdul Bari**](https://www.youtube.com/watch?v=uEUXGcc2VXM)

---

## **Complexity Analysis**

- In the beginning, the array size is n.
- After the first iteration, the array size becomes n/2.
- After the second iteration, the array size becomes n/4 and so on.
- So, after k iterations, the array size becomes n/2<sup>k</sup>.
- The algorithm stops when the array size becomes 1.
  - So, n/2<sup>k</sup> = 1.
  - 2<sup>k</sup> = n.
  - k = log<sub>2</sub>n.
  - The time complexity of the binary search algorithm is O(log<sub>2</sub>n).

- **Time Complexity**:
  - Best Case: O(1): The target element is found at the middle element.
  - Average Case: O(log<sub>2</sub>n): The target element is found after a few iterations.
  - Worst Case: O(log<sub>2</sub>n): The target element is found after a few iterations.
- **Space Complexity**: O(1): The space complexity is constant.

---

## **Calculating the Time Complexity Using Master Method**

- **Master Theorem**: T(n) = a * T(n/b) + f(n<sup>d</sup>)
  - If f(n) = O(n<sup>d</sup>), where d < log<sub>b</sub>a, then T(n) = O(n<sup>log<sub>b</sub>a</sup>)
  - If f(n) = O(n<sup>d</sup>), where d = log<sub>b</sub>a, then T(n) = O(n<sup>d</sup> * log n)
  - If f(n) = O(n<sup>d</sup>), where d > log<sub>b</sub>a, then T(n) = O(f(n))
- **Binary Search**:
  - T(n) = 1 * T(n/2) + O(1)
  - a = 1, b = 2, f(n) = O(1)
  - d = 0, log<sub>2</sub>1 = 0
  - d = log<sub>b</sub>a
  - T(n) = O(log<sub>2</sub>n)
  - **Time Complexity**: O(log<sub>2</sub>n)

---
