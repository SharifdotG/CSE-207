# **CSE 207 - Algorithms - Notes - Merge Sort Algorithm**

<p align="center">
    <img src="https://www.lavivienpost.net/wp-content/uploads/2022/02/merge-sort-400.gif" alt="Merge Sort Algorithm"/>
</p>

---

## **Introduction**

- Merge Sort is a divide and conquer algorithm that was invented by John von Neumann in 1945.
- Merge Sort is a sorting algorithm that sorts an array by dividing it into two halves, sorting the two halves, and then merging them.
- Merge Sort is a stable sorting algorithm.
- Merge Sort is a comparison-based sorting algorithm.
- Merge Sort is a recursive algorithm.

---

## **Divide & Conquer in Merge Sort**

- **Divide**: Divide the array into two halves.
- **Conquer**: Recursively sort the two halves.
- **Combine**: Merge the two sorted halves.

---

## **Algorithm**

1. If the array has only one element, return the array.
2. Calculate the middle of the array.
3. Recursively sort the left half of the array.
4. Recursively sort the right half of the array.
5. Merge the two sorted halves.
6. Return the merged array.
7. The base case of the recursion is when the array has only one element.

---

## **Pseudocode**

```cpp
void merge(int array[], int left, int middle, int right) {
    int n1 = middle - left + 1;
    int n2 = right - middle;

    int leftArray[n1], rightArray[n2];

    for (int i = 0; i < n1; i++) {
        leftArray[i] = array[left + i];
    }

    for (int j = 0; j < n2; j++) {
        rightArray[j] = array[middle + 1 + j];
    }

    int i = 0, j = 0, k = left;

    while (i < n1 && j < n2) {
        if (leftArray[i] <= rightArray[j]) {
            array[k] = leftArray[i];
            i++;
        } else {
            array[k] = rightArray[j];
            j++;
        }
        k++;
    }

    while (i < n1) {
        array[k] = leftArray[i];
        i++, k++;
    }

    while (j < n2) {
        array[k] = rightArray[j];
        j++, k++;
    }
}

void mergeSort(int array[], int left, int right) {
    if (left < right) {
        int middle = left + (right - left) / 2;

        mergeSort(array, left, middle);
        mergeSort(array, middle + 1, right);

        merge(array, left, middle, right);
    }
}
```

- **`merge`** function:
  - **Input**: Array, Left index, Middle index, Right index.
  - **Output**: Merged array.
  - **Steps**:
        1. Calculate the sizes of the two halves.
        2. Create two temporary arrays to store the two halves.
        3. Copy the elements of the two halves into the temporary arrays.
        4. Merge the two halves into the original array.
- **`mergeSort`** function:
  - **Input**: Array, Left index, Right index.
  - **Output**: Sorted array.
  - **Steps**:
        1. If the left index is less than the right index, calculate the middle index.
        2. Recursively sort the left half of the array.
        3. Recursively sort the right half of the array.
        4. Merge the two sorted halves.
        5. The base case of the recursion is when the array has only one element.

---

## **Simulation/Visualization**

<p align="center">
    <img src="https://willrosenbaum.com/assets/img/2022f-cosc-311/merge-sort.gif" alt="Merge Sort Algorithm"/>
</p>

- **Web Based Resources**:
  - [**GeeksforGeeks**](https://www.geeksforgeeks.org/merge-sort/)
  - [**Programiz**](https://www.programiz.com/dsa/merge-sort)
  - [**Javatpoint**](https://www.javatpoint.com/merge-sort)

- **Video Resources**:
  - [**Learn Merge Sort in 13 minutes 🔪 - Bro Code**](https://www.youtube.com/watch?v=3j0SWDX4AtU)
  - [**Merge sort in 3 minutes - Michael Sambol**](https://www.youtube.com/watch?v=4VqmGXwpLqc)
  - [**2.7.2. Merge Sort Algorithm - Abdul Bari**](https://www.youtube.com/watch?v=mB5HXBb_HY8)

---

## **Complexity Analysis**

- **Divide Step**:
  - Each time the array is divided into two halves.
  - So, the time complexity of the divide step is O(log<sub>2</sub>n).
- **Conquer Step**:
  - The conquer step is the time taken to merge the two sorted halves.
  - The time complexity of the conquer step is O(n).
- **Overall Time Complexity**: O(n log<sub>2</sub>n).

- **Time Complexity**:
  - Best Case: O(n log<sub>2</sub>n)
  - Average Case: O(n log<sub>2</sub>n)
  - Worst Case: O(n log<sub>2</sub>n)
- **Space Complexity**: O(n): The space complexity of the **merge sort** algorithm is **linear**. Because the algorithm uses an extra array to store the two halves.

## **Calculating the Time Complexity Using Master Method**

- **Master Theorem**: T(n) = a * T(n/b) + f(n<sup>d</sup>)
  - If f(n) = O(n<sup>d</sup>), where d < log<sub>b</sub>a, then T(n) = O(n<sup>log<sub>b</sub>a</sup>)
  - If f(n) = O(n<sup>d</sup>), where d = log<sub>b</sub>a, then T(n) = O(n<sup>d</sup> * log n)
  - If f(n) = O(n<sup>d</sup>), where d > log<sub>b</sub>a, then T(n) = O(f(n))
- **Merge Sort**:
  - T(n) = 2 * T(n/2) + O(n)
  - a = 2, b = 2, f(n) = O(n)
  - d = 1, log<sub>2</sub>2 = 1
  - T(n) = O(n log<sub>2</sub>n)
  - **Time Complexity**: O(n log<sub>2</sub>n)

---
