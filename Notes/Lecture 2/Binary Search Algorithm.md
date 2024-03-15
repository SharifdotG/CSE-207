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

1. Star

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
