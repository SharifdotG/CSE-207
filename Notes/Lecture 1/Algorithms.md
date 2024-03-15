# **CSE 207 - Algorithms - Notes - Algorithm**

![Alt Text](https://i.pinimg.com/originals/63/64/77/636477067a9206def4911cbb9c317576.gif)

---

## **What is an Algorithm?**

- A process or set of rules to be followed in calculations or other problem-solving operations, especially by a computer.
- In Computer Science, an algorithm is a set of steps for a computer program to accomplish a task.
- An algorithm is a finite set of instructions that, if followed, accomplishes a particular task.
- An algorithm is a sequence of unambiguous instructions for solving a problem, i.e., for obtaining a required output for any legitimate input in a finite amount of time.
- An algorithm is a tool for solving a well-specified computational problem.

---

## **Where do we need Algorithms?**

- **Search Engines**: Google, Bing, Yahoo, etc.
- **Social Media**: Facebook, Twitter, Instagram, etc.
- **E-commerce**: Amazon, eBay, Alibaba, etc.
- **Operating Systems**: Windows, Linux, MacOS, etc.
- **Databases**: MySQL, Oracle, MongoDB, etc.
- **Networking**: Routers, Switches, etc.
- **Graphics**: Games, Movies, etc.
- **Artificial Intelligence**: Machine Learning, Deep Learning, etc.
- **Robotics**: Drones, Self-driving cars, etc.
- **Cybersecurity**: Antivirus, Firewalls, etc.
- **Healthcare**: Medical Imaging, Drug Discovery, etc.
- **Finance**: Stock Market, Banking, etc.
- **Education**: E-learning, E-books, etc.
- **Transportation**: Traffic Management, GPS, etc.
- **Weather Forecasting**: Meteorology, Climate Change, etc.
- **Space Exploration**: NASA, SpaceX, etc.
- **Defense**: Military, Homeland Security, etc.
- **Entertainment**: Music, Video, etc.
- **Communication**: Email, Chat, etc.
- **Gaming**: Video Games, Board Games, etc.
- **Sports**: Analytics, Betting, etc.
- **Agriculture**: Farming, Food Supply, etc.

---

## **What makes an algorithm good?**

- **Correctness**: An algorithm should be able to solve the problem it is designed for.
- **Efficiency**: An algorithm should be able to solve the problem within a reasonable amount of time.
- **Simplicity**: An algorithm should be simple enough to understand and implement.
- **Optimality**: An algorithm should be able to solve the problem with the best possible solution.
- **Scalability**: An algorithm should be able to solve the problem for any input size.
- **Adaptability**: An algorithm should be able to solve the problem for any input type.
- **Robustness**: An algorithm should be able to solve the problem for any input condition.
- **Maintainability**: An algorithm should be able to solve the problem for any input change.

### **Performance Evaluation**

#### **Finiding GCD of two numbers**

- **Algorithm 1**: Euclid's Algorithm
- **Algorithm 2**: Prime Factorization

##### **Algorithm 1: Euclid's Algorithm**

- **Step 1**: While n1 is divisible by n2
- **Step 2**: Calculate the remainder r = n1 % n2
- **Step 3**: Set n1 = n2 and n2 = r
- **Step 4**: Return n2

###### **Example**

- **Input**: n1 = 8, n2 = 36
- **Output**: 4
- **Steps**:
  - 36 % 8 = 4
  - 8 % 4 = 0
  - **GCD**: 4

##### **Algorithm 2: Prime Factorization**

- **Step 1**: Find the prime factors of n1 and n2
- **Step 2**: Find the common prime factors
- **Step 3**: Multiply the common prime factors
- **Step 4**: Return the result

###### **Example**

- **Input**: n1 = 8, n2 = 36
- **Output**: 4
- **Steps**:
  - Prime Factors of 8: 2, 2, 2
  - Prime Factors of 36: 2, 2, 3, 3
  - **Common Prime Factors**: 2, 2
  - **GCD**: 4

##### **Comparing the number of operations**

- **Algorithm 1**: Euclid's Algorithm

  - **Input**: n1 = 12, n2 = 8
  - **Operations**:
    - 12 % 8 = 4
    - 8 % 4 = 0
    - **GCD**: 4
    - **Total Operations**: 2

- **Algorithm 2**: Prime Factorization

  - **Input**: n1 = 12, n2 = 8
  - **Operations**:
    - Prime Factors of 12: 2, 2, 3
    - Prime Factors of 8: 2, 2, 2
    - **Common Prime Factors**: 2, 2
    - **GCD**: 4
    - **Total Operations**: 3

##### **Conclusion**

Though both algorithms are correct, Euclid's Algorithm is more efficient than Prime Factorization as it requires fewer operations. Therefore, Euclid's Algorithm is a better choice for finding the GCD of two numbers. That's how we can evaluate the performance of an algorithm.

---
