# **CSE 207 - Algorithms - Notes - Job Sequencing with Deadline**

<p align="center">
    <img src="https://miro.medium.com/v2/resize:fit:648/1*fCm4EwGIm_KFvHrniNR_yw.jpeg" alt="Job Sequencing with Deadline"/>
</p>

---

## **Introduction**

- **Job Sequencing with Deadline** is also a problem in combinatorial optimization.
- Here you are given a set of **n** jobs, where each job **i** has a deadline **d<sub>i</sub>** and a profit **p<sub>i</sub>**.
- The profit **p<sub>i</sub>** is earned if the job is completed on or before the deadline.
- Only one job can be scheduled at a time.
- The objective is to find the maximum profit that can be earned by scheduling the jobs.
- This problem can be solved using **Greedy Algorithm**.

---

## **Job Sequencing with Deadline - Greedy Approach**

- Suppose we have **5** jobs with the following deadlines and profits:

| Job ID | 1 | 2 | 3 | 4 | 5 |
| --- | --- | --- | --- | --- | --- |
| Deadline | 2 | 1 | 2 | 1 | 3 |
| Profit | 100 | 19 | 27 | 25 | 15 |

- The Optimal Solution is to schedule the jobs in the following order: **5, 1, 3**.
- The output will be **142**.

- First, we will sort the jobs in descending order of their profits.
- Then we have to initialize an empty schedule and an array to keep track of the slots.
- We will iterate through the jobs and for each job, we will find the latest slot available before the deadline and assign the job to that slot. We have to do the following:
  - Assign the job to the latest slot available before the deadline.
  - If the slot is available, we will assign the job to that slot and mark the slot as occupied.
  - If the slot is not available, we will move to the previous slot and repeat the process until we find an available slot.
  - If no slot is available, we will skip the job.
- Finally, we will calculate the total profit earned by scheduling the jobs.
- The output will be the total profit earned.

---

## **Algorithm**

- The **Greedy Algorithm** to solve the **Job Sequencing with Deadline** problem is as follows:

1. Sort the jobs in descending order of their profits.

---

## **Pseudocode**

- The **Pseudocode** for the **Greedy Algorithm** to solve the **Job Sequencing with Deadline** problem is as follows:

```cpp
JobSequencing(int jobs[], int n) {
    sort(jobs, jobs + n, compare);

    int result[n];
    bool slot[n];

    for (int i = 0; i < n; i++) {
        slot[i] = false;
    }

    for (int i = 0; i < n; i++) {
        for (int j = min(n, jobs[i].deadline) - 1; j >= 0; j--) {
            if (slot[j] == false) {
                result[j] = i;
                slot[j] = true;
                break;
            }
        }
    }

    return result;
}
```

- The **JobSequencing** function sorts the jobs in descending order of their profits and initializes an empty schedule and an array to keep track of the slots.
- Then it iterates through the jobs and for each job, it finds the latest slot available before the deadline and assigns the job to that slot.
- Finally, it calculates the total profit earned by scheduling the jobs and returns the total profit earned.

---

## **Complexity Analysis**

- Best Case Time Complexity: **O(nlogn)**
- Average Case Time Complexity: **O(nlogn)**
- Worst Case Time Complexity: **O(nlogn)**
- Space Complexity: **O(n)**

---

## **Simulation/Visualization**

<p align="center">
    <img src="https://lh4.googleusercontent.com/oPnEMwtHivvA7Uy36G1lSQSraQ6xJ__THJJ3XiLL3mP--VgNerwFaPZgfXWbS3WDFYn2EKL8WiG3VDu3fAtB5Ii3ZFiT5-Ln8XmM1_zwH0Q7sTg_28NYWBDOP07_MQ" alt="Job Sequencing with Deadline - Greedy Algorithm"/>
</p>

- **Web Based Resources**:
  - [**GeeksforGeeks**](https://www.geeksforgeeks.org/job-sequencing-problem/)
  - [**Tutorialspoint**](https://www.tutorialspoint.com/data_structures_algorithms/job_sequencing_with_deadline.htm)

- **Video Resources**:
  - [**3.2 Job Sequencing with Deadlines - Greedy Method - Abdul Bari**](https://www.youtube.com/watch?v=zPtI8q9gvX8)
  - [**Job Sequencing Problem (Greedy Algorithm) | GeeksforGeeks - GeeksforGeeks**](https://www.youtube.com/watch?v=R6Skj4bT1HE)

---
