# **CSE 207 - Algorithms - Notes - Min-Max Algorithm**

<p align="center">
    <img src="https://res.cloudinary.com/codecrucks/images/f_webp,q_auto/v1633008733/max-min-problem/max-min-problem.jpg?_i=AA" alt="Min-Max Algorithm"/>
</p>

---

## **Introduction**

- Min-Max Algorithm is a divide and conquer algorithm that was invented by John von Neumann in 1945.
- Min-Max Algorithm is an algorithm that finds the minimum and maximum elements in an array.
- Min-Max Algorithm is a divide and conquer algorithm.
- Min-Max Algorithm is an in-place algorithm.

---

## **Divide & Conquer in Min-Max Algorithm**

- **Divide**: Divide the array into two sub-arrays.
- **Conquer**: Find the minimum and maximum elements in the two sub-arrays.
- **Combine**: Compare the minimum and maximum elements of the two sub-arrays to find the minimum and maximum elements of the entire array.

---

## **Algorithm**

1. If the array has only one element, return the array.
2. If the array has only two elements, compare the two elements and return the minimum and maximum elements.
3. Divide the array into two sub-arrays.
4. Recursively find the minimum and maximum elements in the two sub-arrays.
5. Compare the minimum and maximum elements of the two sub-arrays to find the minimum and maximum elements of the entire array.
6. Return the minimum and maximum elements of the entire array.
7. The base case of the recursion is when the array has only one or two elements.

---

## **Pseudocode**

```cpp
void minMax(int array[], int left, int right, int &min, int &max) {
    if (left == right) {
        min = max = array[left];
    } else if (right - left == 1) {
        if (array[left] < array[right]) {
            min = array[left];
            max = array[right];
        } else {
            min = array[right];
            max = array[left];
        }
    } else {
        int mid = (left + right) / 2;
        int min1, max1, min2, max2;
        minMax(array, left, mid, min1, max1);
        minMax(array, mid + 1, right, min2, max2);
        min = min1 < min2 ? min1 : min2;
        max = max1 > max2 ? max1 : max2;
    }
}
```

---

## **Simulation/Vizualization**

<p align="center">
    <img src="https://res.cloudinary.com/codecrucks/images/c_scale,w_378,h_434,dpr_2/f_webp,q_auto/v1633009264/max-min-problem-using-divide-and-conquer/max-min-problem-using-divide-and-conquer.png?_i=AA" alt="Quick Sort Algorithm"/>
</p>

- **Web Based Resources**:
  - [**Tutorialspoint**](https://www.tutorialspoint.com/data_structures_algorithms/max_min_problem.htm)
  - [**DigitalBitHub**](https://www.digitalbithub.com/learn/finding-minimum-and-maximum-application-of-divide-and-conquer)

- **Video Resources**:
  - [**Min Max Algorithm with Divide & Conquer🏆 - Gate Smashers**](https://www.youtube.com/watch?v=g8DJiGWoQmk)

---

## **Complexity Analysis**

- **Time Complexity**:
  - Best Case: O(n)
  - Average Case: O(n)
  - Worst Case: O(n)
- **Space Complexity**: O(1)

---

## **Calculating the Time Complexity Using Master Method**

- **Master Theorem**: T(n) = a * T(n/b) + f(n<sup>d</sup>)
  - If f(n) = O(n<sup>d</sup>), where d < log<sub>b</sub>a, then T(n) = O(n<sup>log<sub>b</sub>a</sup>)
  - If f(n) = O(n<sup>d</sup>), where d = log<sub>b</sub>a, then T(n) = O(n<sup>d</sup> * log n)
  - If f(n) = O(n<sup>d</sup>), where d > log<sub>b</sub>a, then T(n) = O(f(n))
- **Min-Max Algorithm**:
  - T(n) = 2 * T(n/2) + O(n)
  - a = 2, b = 2, f(n) = n
  - d = 1, log<sub>2</sub>2 = 1
  - d < log<sub>b</sub>a
  - T(n) = O(n<sup>log<sub>2</sub>2</sup>) = O(n)
  - **Time Complexity**: O(n)

---