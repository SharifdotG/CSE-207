# **CSE 207 - Algorithms - Notes - Quick Sort Algorithm**

<p align="center">
    <img src="https://fullyunderstood.com/wp-content/uploads/2019/09/quicksort.gif" alt="Quick Sort Algorithm"/>
</p>

---

## **Introduction**

- Quick Sort is a divide and conquer algorithm that was invented by Tony Hoare in 1959.
- Quick Sort is a sorting algorithm that sorts an array by selecting a 'pivot' element from the array and partitioning the other elements into two sub-arrays according to whether they are less than or greater than the pivot.
- Quick Sort is an in-place sorting algorithm.

---

## **Divide & Conquer in Quick Sort**

- **Divide**: Select a 'pivot' element from the array.
- **Conquer**: Partition the array into two sub-arrays according to whether they are less than or greater than the pivot.
- **Combine**: Recursively sort the two sub-arrays.

---

## **Algorithm**

1. If the array has only one element, return the array.
2. Select a 'pivot' element from the array.
3. Partition the array into two sub-arrays according to whether they are less than or greater than the pivot.
4. Recursively sort the two sub-arrays.
5. Return the sorted array.
6. The base case of the recursion is when the array has only one element.
7. The pivot can be selected in different ways:
    - First element as pivot.
    - Last element as pivot.
    - Random element as pivot.
    - Median element as pivot.

- The choice of pivot can affect the running time of Quick Sort.

---

## **Pseudocode**

```cpp
int partition(int array[], int left, int right) {
    int pivot = array[right];
    int i = left - 1;

    for (int j = left; j < right; j++) {
        if (array[j] < pivot) {
            i++;
            swap(array[i], array[j]);
        }
    }

    swap(array[i + 1], array[right]);

    return i + 1;
}

void quickSort(int array[], int left, int right) {
    if (left < right) {
        int pivot = partition(array, left, right);

        quickSort(array, left, pivot - 1);
        quickSort(array, pivot + 1, right);
    }
}
```

- **`partition`** function:
  - The `partition` function takes the last element as the pivot, places the pivot element at its correct position in the sorted array, and places all smaller elements (smaller than the pivot) to the left of the pivot and all greater elements to the right of the pivot.
  - The `partition` function returns the position of the pivot element.
- **`quickSort`** function:
  - The `quickSort` function is a recursive function that takes the array, the left index, and the right index as parameters.
  - The `quickSort` function calls the `partition` function to partition the array and then recursively calls itself to sort the two sub-arrays.
  - The base case of the recursion is when the array has only one element.

---

## **Simulation/Vizualization**

<p align="center">
    <img src="https://www.tutorialspoint.com/data_structures_algorithms/images/quick_sort_partition_animation.gif" alt="Quick Sort Algorithm"/>
</p>

- **Web Based Resources**:
  - [**GeeksforGeeks**](https://www.geeksforgeeks.org/quick-sort/)
  - [**Programiz**](https://www.programiz.com/dsa/quick-sort)
  - [**JavaTPoint**](https://www.javatpoint.com/quick-sort)
- **Video Resources**:
  - [**2.8.1 QuickSort Algorithm - Abdul Bari**](https://www.youtube.com/watch?v=7h1s2SojIRw)
  - [**Learn Quick Sort in 13 minutes ⚡ - Bro Code**](https://www.youtube.com/watch?v=Vtckgz38QHs)
  - [**Quick sort in 4 minutes - Michael Sambol**](https://www.youtube.com/watch?v=Hoixgm4-P4M)

---

## **Complexity Analysis**

- **Time Complexity**:
  - **Best Case**: O(n log n)
  - **Average Case**: O(n log n)
  - **Worst Case**: O(n^2)
- **Space Complexity**: O(log n)

---

## **Calculating the Time Complexity Using Master Method**

- **Master Theorem**: T(n) = a * T(n/b) + f(n<sup>d</sup>)
  - If f(n) = O(n<sup>d</sup>), where d < log<sub>b</sub>a, then T(n) = O(n<sup>log<sub>b</sub>a</sup>)
  - If f(n) = O(n<sup>d</sup>), where d = log<sub>b</sub>a, then T(n) = O(n<sup>d</sup> * log n)
  - If f(n) = O(n<sup>d</sup>), where d > log<sub>b</sub>a, then T(n) = O(f(n))
- **Quick Sort**:
  - T(n) = 2 * T(n/2) + O(n)
  - a = 2, b = 2, f(n) = O(n)
  - d = 1, log<sub>2</sub>2 = 1
  - d = log<sub>b</sub>a
  - T(n) = O(n log<sub>2</sub>n)
  - **Time Complexity**: O(n log<sub>2</sub>n)

---
