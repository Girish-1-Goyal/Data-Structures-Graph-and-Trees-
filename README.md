# C++ Programming: Basics to Advanced

This markdown document covers the essential topics of C++ programming, from basic to advanced concepts. Each topic includes definitions, examples, and output for better understanding.

---

## Table of Contents
1. [Introduction](#introduction)
2. [Basic Syntax](#basic-syntax)
3. [Data Types](#data-types)
4. [Variables and Constants](#variables-and-constants)
5. [Control Flow](#control-flow)
   - [if-else Statements](#if-else-statements)
   - [Switch Case](#switch-case)
   - [Loops](#loops)
6. [Functions](#functions)
7. [Object-Oriented Programming (OOP)](#object-oriented-programming-oop)
   - [Classes and Objects](#classes-and-objects)
   - [Inheritance](#inheritance)
   - [Polymorphism](#polymorphism)
   - [Encapsulation](#encapsulation)
   - [Abstraction](#abstraction)
   - [Operator Overloading](#operator-overloading)
   - [Friend Functions](#friend-functions)
   - [Virtual Functions](#virtual-functions)
8. [Advanced Topics](#advanced-topics)
   - [Templates](#templates)
   - [STL (Standard Template Library)](#stl-standard-template-library)
   - [File Handling](#file-handling)
   - [Multithreading](#multithreading)
   - [Lambda Expressions](#lambda-expressions)
   - [Smart Pointers](#smart-pointers)
   - [Move Semantics](#move-semantics)

---

## Introduction
C++ is a general-purpose programming language created by Bjarne Stroustrup. It is widely used for system programming, game development, and competitive programming. C++ supports both procedural and object-oriented programming paradigms.

---

## Basic Syntax
Every C++ program starts with the `main` function. Here's a simple "Hello, World!" program:

```cpp
#include <iostream>
using namespace std;

int main() {
    cout << "Hello, World!" << endl;
    return 0;
}
```

**Output:**
```
Hello, World!
```

---

## Data Types
C++ provides several built-in data types for different purposes.

### Basic Data Types
- `int`: Integer numbers
- `float`: Floating-point numbers
- `double`: Double-precision floating-point numbers
- `char`: Single character
- `bool`: Boolean (true or false)

Example:
```cpp
#include <iostream>
using namespace std;

int main() {
    int age = 25;
    float height = 5.9;
    char grade = 'A';
    bool isStudent = true;

    cout << "Age: " << age << endl;
    cout << "Height: " << height << endl;
    cout << "Grade: " << grade << endl;
    cout << "Is Student: " << isStudent << endl;

    return 0;
}
```

**Output:**
```
Age: 25
Height: 5.9
Grade: A
Is Student: 1
```

---

## Variables and Constants

### Variables
Variables are used to store data in memory.
```cpp
int x = 10; // integer variable
```

### Constants
Constants are immutable values defined using `const`.
```cpp
const float PI = 3.14159;
```

---

## Control Flow
### if-else Statements

```cpp
#include <iostream>
using namespace std;

int main() {
    int number = 10;

    if (number > 0) {
        cout << "Number is positive." << endl;
    } else {
        cout << "Number is not positive." << endl;
    }

    return 0;
}
```

**Output:**
```
Number is positive.
```

### Switch Case
```cpp
#include <iostream>
using namespace std;

int main() {
    int day = 3;

    switch (day) {
        case 1:
            cout << "Monday";
            break;
        case 2:
            cout << "Tuesday";
            break;
        case 3:
            cout << "Wednesday";
            break;
        default:
            cout << "Other day";
    }

    return 0;
}
```

**Output:**
```
Wednesday
```

---

## Loops

### For Loop
```cpp
for (int i = 0; i < 5; i++) {
    cout << i << endl;
}
```

### While Loop
```cpp
int i = 0;
while (i < 5) {
    cout << i << endl;
    i++;
}
```

---

## Functions
Functions allow code reuse and modularity.

```cpp
#include <iostream>
using namespace std;

int add(int a, int b) {
    return a + b;
}

int main() {
    int result = add(5, 3);
    cout << "Sum: " << result << endl;
    return 0;
}
```

**Output:**
```
Sum: 8
```

---

## Object-Oriented Programming (OOP)

### Classes and Objects
```cpp
#include <iostream>
using namespace std;

class Car {
public:
    string brand;
    int speed;

    void display() {
        cout << "Brand: " << brand << ", Speed: " << speed << endl;
    }
};

int main() {
    Car car1;
    car1.brand = "Toyota";
    car1.speed = 120;
    car1.display();

    return 0;
}
```

**Output:**
```
Brand: Toyota, Speed: 120
```

### Inheritance
```cpp
#include <iostream>
using namespace std;

class Vehicle {
public:
    string type;
};

class Car : public Vehicle {
public:
    string brand;
};
```

### Polymorphism
```cpp
#include <iostream>
using namespace std;

class Shape {
public:
    virtual void draw() {
        cout << "Drawing Shape" << endl;
    }
};

class Circle : public Shape {
public:
    void draw() override {
        cout << "Drawing Circle" << endl;
    }
};

int main() {
    Shape *shape;
    Circle circle;
    shape = &circle;
    shape->draw();
    return 0;
}
```

**Output:**
```
Drawing Circle
```

### Encapsulation
Encapsulation is the bundling of data and methods into a single unit (class).
```cpp
#include <iostream>
using namespace std;

class Employee {
private:
    int salary;

public:
    void setSalary(int s) {
        salary = s;
    }

    int getSalary() {
        return salary;
    }
};

int main() {
    Employee emp;
    emp.setSalary(50000);
    cout << "Salary: " << emp.getSalary() << endl;
    return 0;
}
```

**Output:**
```
Salary: 50000
```

### Abstraction
```cpp
#include <iostream>
using namespace std;

class AbstractClass {
public:
    virtual void display() = 0; // Pure virtual function
};

class ConcreteClass : public AbstractClass {
public:
    void display() override {
        cout << "Implementing Abstract Function" << endl;
    }
};

int main() {
    ConcreteClass obj;
    obj.display();
    return 0;
}
```

**Output:**
```
Implementing Abstract Function
```

### Operator Overloading
```cpp
#include <iostream>
using namespace std;

class Complex {
public:
    int real, imag;

    Complex(int r, int i) : real(r), imag(i) {}

    Complex operator + (const Complex &obj) {
        return Complex(real + obj.real, imag + obj.imag);
    }

    void display() {
        cout << real << " + " << imag << "i" << endl;
    }
};

int main() {
    Complex c1(1, 2), c2(3, 4);
    Complex c3 = c1 + c2;
    c3.display();
    return 0;
}
```

**Output:**
```
4 + 6i
```

### Friend Functions
```cpp
#include <iostream>
using namespace std;

class Box {
private:
    int width;

public:
    Box(int w) : width(w) {}

    friend void printWidth(Box b);
};

void printWidth(Box b) {
    cout << "Width: " << b.width << endl;
}

int main() {
    Box box(10);
    printWidth(box);
    return 0;
}
```

**Output:**
```
Width: 10
```

### Virtual Functions
```cpp
#include <iostream>
using namespace std;

class Base {
public:
    virtual void show() {
        cout << "Base class" << endl;
    }
};

class Derived : public Base {
public:
    void show() override {
        cout << "Derived class" << endl;
    }
};

int main() {
    Base *basePtr;
    Derived derivedObj;
    basePtr = &derivedObj;
    basePtr->show();
    return 0;
}
```

**Output:**
```
Derived class
```

---

## Advanced Topics

### Templates
```cpp
template <typename T>
T add(T a, T b) {
    return a + b;
}

int main() {
    cout << add(5, 3) << endl;
    cout << add(5.5, 3.3) << endl;
    return 0;
}
```

**Output:**
```
8
8.8
```

### STL (Standard Template Library)
```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    vector<int> numbers = {1, 2, 3};
    for (int num : numbers) {
        cout << num << " ";
    }
    return 0;
}
```

**Output:**
```
1 2 3
```

### File Handling
```cpp
#include <fstream>
using namespace std;

int main() {
    ofstream file("example.txt");
    file << "Hello, File!";
    file.close();

    ifstream readFile("example.txt");
    string content;
    readFile >> content;
    cout << content << endl;
    return 0;
}
```

**Output:**
```
Hello, File!
```

### Lambda Expressions
```cpp
#include <iostream>
using namespace std;

int main() {
    auto add = [](int a, int b) { return a + b; };
    cout << "Sum: " << add(3, 4) << endl;
    return 0;
}
```

**Output:**
```
Sum: 7
```

### Smart Pointers
```cpp
#include <iostream>
#include <memory>
using namespace std;

int main() {
    unique_ptr<int> ptr = make_unique<int>(10);
    cout << "Value: " << *ptr << endl;
    return 0;
}
```

**Output:**
```
Value: 10
```

### Move Semantics
```cpp
#include <iostream>
#include <utility>
using namespace std;

class MoveExample {
public:
    int* data;

    MoveExample(int value) {
        data = new int(value);
        cout << "Resource acquired" << endl;
    }

    MoveExample(MoveExample&& obj) noexcept {
        data = obj.data;
        obj.data = nullptr;
        cout << "Resource moved" << endl;
    }

    ~MoveExample() {
        delete data;
        cout << "Resource destroyed" << endl;
    }
};

int main() {
    MoveExample obj1(10);
    MoveExample obj2 = move(obj1);
    return 0;
}
```

**Output:**
```
Resource acquired
Resource moved
Resource destroyed
```

---

This markdown file provides a comprehensive overview of C++ from basic to advanced levels. Explore each section to strengthen your understanding of C++.


# Mastering Data Structures and Algorithms (DSA)

To tackle Data Structures and Algorithms (DSA) problems effectively, follow these strategies and patterns:

---

## 1. **Understand the Problem**
- **Read the problem statement carefully.**
- **Identify inputs and outputs:** Determine what is provided and what needs to be found.
- **Clarify constraints:** Consider edge cases, size limits, and performance expectations.
- **Ask questions:** If unclear, make assumptions explicit in your solution.

---

## 2. **Choose the Right Data Structure**
- **Array:** For sequential data or when indices are important.
- **HashMap/HashSet:** Fast lookups or uniqueness constraints.
- **Stack/Queue:** For LIFO/FIFO behavior.
- **Heap/Priority Queue:** Quickly access the smallest or largest element.
- **Tree/Graph:** Hierarchical or networked relationships.
- **Linked List:** Dynamic insertions and deletions.
- **Sliding Window:** Subarrays or substrings processing.

---

## 3. **Common Problem-Solving Patterns**

### Two Pointers
- **When to use:** Optimizing space/time complexity in arrays or strings.
- **Examples:** Palindrome checking, merging sorted arrays, finding pairs with a given sum.

### Sliding Window
- **When to use:** Subarray or substring problems.
- **Examples:** Maximum sum of k-length subarray, longest substring without repeating characters.

### Binary Search
- **When to use:** Searching sorted data or optimizing an objective.
- **Examples:** Finding square roots, searching rotated arrays.

### Divide and Conquer
- **When to use:** Problems that can be divided into smaller sub-problems.
- **Examples:** Merge Sort, Maximum subarray sum.

### Backtracking
- **When to use:** Generating all possibilities or solving constraints.
- **Examples:** N-Queens, Sudoku solver.

### Dynamic Programming (DP)
- **When to use:** Problems with overlapping sub-problems.
- **Examples:** Knapsack, Longest Increasing Subsequence.

### Greedy Algorithms
- **When to use:** Local optimization leads to a global solution.
- **Examples:** Interval scheduling, Huffman encoding.

### Graph Traversal
- **BFS:** Shortest path in an unweighted graph.
- **DFS:** Exploring all paths or connected components.
- **Examples:** Maze problems, detecting cycles.

### Union-Find
- **When to use:** Connected components or cycle detection.
- **Examples:** Kruskal’s algorithm.

### Topological Sorting
- **When to use:** Dependency or order-based problems.
- **Examples:** Course schedule, task scheduling.

---

## 4. **Break Down the Problem**
- Write a **high-level plan** for your solution.
- Solve a **simpler version** or focus on a smaller part.
- Create **helper functions** for repetitive tasks.

---

## 5. **Optimize and Analyze**
- **Time complexity:** Is your solution efficient? Can it be improved?
- **Space complexity:** Are there redundant data structures?
- **Test edge cases:** Empty inputs, max/min constraints, duplicates.

---

## 6. **Practice Patterns**
- Solve categorized problems to build pattern recognition.
- Start with easy problems and progress to harder ones.
- Platforms: **LeetCode**, **Codeforces**, **HackerRank**.

---

## 7. **Learn from Mistakes**
- Review your approach after getting stuck or seeing solutions.
- Focus on **why** an algorithm works, not just implementation.

---

## Time Allocation Summary
| **Step**                  | **Time Investment**       |
|---------------------------|---------------------------|
| **Problem Understanding** | 5–10 minutes             |
| **Devising a Strategy**   | 10–15 minutes            |
| **Breaking Down the Problem** | 10–15 minutes        |
| **Writing Pseudocode**    | 10–15 minutes            |
| **Coding and Debugging**  | 20–30 minutes            |
| **Iterative Optimization**| 15–20 minutes            |
| **Process Review**        | 5–10 minutes             |

---

## 10 Dynamic Programming (DP) Patterns

### 1) **1D DP Problems**
- Fibonacci Sequence
- Climbing Stairs
- Coin Change
- House Robber

### 2) **2D DP Problems**
- Grid-based Problems (e.g., Minimum Path Sum)
- Knapsack Problem
- Longest Common Subsequence
- Edit Distance

### 3) **Substring/Subsequence Problems**
- Longest Increasing Subsequence
- Longest Palindromic Substring
- Palindrome Partitioning

### 4) **Partition Problems**
- Partition Equal Subset Sum
- Palindromic Partitioning

### 5) **Game Theory Problems**
- Stone Game
- Nim Game

### 6) **Interval DP Problems**
- Matrix Chain Multiplication
- Burst Balloons

### 7) **Tree DP Problems**
- Binary Tree Maximum Path Sum
- Longest Path in a Tree

### 8) **Bitmask DP Problems**
- Traveling Salesman Problem (TSP)
- Steiner Tree

### 9) **Digit DP**
- Number of Digit One

### 10) **Others**
- Catalan Numbers
- Subset Sum Problem

---

## 10 Graph Patterns

### 1. Graph Traversal
- BFS: **LeetCode 127 - Word Ladder**
- DFS: **LeetCode 200 - Number of Islands**

### 2. Shortest Path
- Dijkstra’s: **LeetCode 743 - Network Delay Time**
- Bellman-Ford: **LeetCode 787 - Cheapest Flights**

### 3. Minimum Spanning Tree (MST)
- Kruskal’s: **LeetCode 1135 - Connecting Cities**
- Prim’s: **LeetCode 1584 - Min Cost**

### 4. Topological Sorting
- Topological Sort: **LeetCode 207 - Course Schedule**
- Kahn’s Algorithm: **LeetCode 210 - Course Schedule II**

### 5. Connected Components
- LeetCode 323 - Number of Connected Components

### 6. Cycle Detection
- LeetCode 207 - Course Schedule

### 7. Graph Coloring
- Bipartite Check: **LeetCode 785**
- M-Coloring: **LeetCode 1042**

### 8. Flow Problems
- Max Flow: **LeetCode 1334**

### 9. Union-Find
- Union-Find: **LeetCode 684**
- Cycle Detection: **LeetCode 261**

### 10. Advanced Graph Problems
- Traveling Salesman Problem (TSP) using Bitmask DP

---

Mastering these strategies, patterns, and techniques will significantly enhance your ability to solve DSA problems confidently.

# Time Complexity of Algorithms

## Arrays (Space-Time Complexity)

| Operation              | Worst Case | Average Case | Best Case |
|------------------------|------------|--------------|-----------|
| Accessing an element   | O(1)       | O(1)         | O(1)      |
| Updating an element    | O(1)       | O(1)         | O(1)      |
| Deleting an element    | O(n)       | O(n)         | O(1)      |
| Inserting an element   | O(n)       | O(n)         | O(1)      |
| Searching for an element | O(n)     | O(n)         | O(1)      |

---

## Algorithm Complexity

### Sorting Algorithms

| Algorithm      | Worst Case    | Average Case | Best Case     | Space Complexity |
|----------------|---------------|--------------|---------------|-------------------|
| Quicksort      | O(n²)         | O(n log n)   | O(n log n)    | O(log n)         |
| Mergesort      | O(n log n)    | O(n log n)   | O(n log n)    | O(n)             |
| Heapsort       | O(n log n)    | O(n log n)   | O(n log n)    | O(1)             |
| Bubble Sort    | O(n²)         | O(n²)        | O(n)          | O(1)             |
| Insertion Sort | O(n²)         | O(n²)        | O(n)          | O(1)             |
| Selection Sort | O(n²)         | O(n²)        | O(n²)         | O(1)             |

---

### Searching Algorithms

| Algorithm          | Worst Case    | Average Case | Best Case     | Space Complexity |
|--------------------|---------------|--------------|---------------|-------------------|
| Binary Search      | O(log n)      | O(log n)     | O(1)          | O(1)             |
| Linear Search      | O(n)          | O(n)         | O(1)          | O(1)             |

---

## Strings (Space-Time Complexity)

| Operation         | Worst Case     | Average Case  | Best Case      |
|-------------------|----------------|---------------|----------------|
| Accessing         | O(1)          | O(1)          | O(1)           |
| Deleting          | O(n)          | O(n)          | O(1)           |
| Inserting         | O(n)          | O(n)          | O(1)           |
| Searching         | O(n * m)      | O(n)          | O(1)           |
| Slicing           | O(n)          | O(n)          | O(n)           |
| Concatenating     | O(n + m)      | O(n + m)      | O(n)           |
| Comparison        | O(n)          | O(n)          | O(n)           |

---

### String Search Algorithms

| Algorithm               | Worst Case        | Average Case    | Best Case    | Space Complexity |
|-------------------------|-------------------|-----------------|-------------|-------------------|
| Radix Sort (m = length) | O(n * m)         | O(n * m)        | O(n * m)    | O(n + m)         |
| Naive Search            | O(m * (n - m + 1)) | O(n * m)      | O(n)        | O(1)             |
| Knuth-Morris-Pratt      | O(m + n)         | O(n)            | O(n)        | O(m)             |
| Boyer-Moore             | O(n * m)         | O(n)            | O(n/m)      | O(m)             |
| Rabin-Karp              | O(m * (n - m + 1)) | O(n + m)      | O(m)        | O(m)             |

---

## Linked Lists (Space-Time Complexity)

| Operation              | Worst Case | Average Case | Best Case |
|------------------------|------------|--------------|-----------|
| Accessing             | O(n)       | O(n)         | O(1)      |
| Deleting (after search) | O(1)     | O(1)         | O(1)      |
| Inserting (after search) | O(1)   | O(1)         | O(1)      |
| Searching              | O(n)       | O(n)         | O(1)      |
| Traversing             | O(n)       | O(n)         | O(n)      |

---

## Trees (Space-Time Complexity)

| Operation            | Worst Case | Average Case | Best Case | Space Complexity |
|----------------------|------------|--------------|-----------|-------------------|
| Depth-First Search   | O(n)       | O(n)         | O(n)      | O(n)             |
| Breadth-First Search | O(n)       | O(n)         | O(n)      | O(n)             |
| Tree Sort            | O(n²)      | O(n log n)   | O(n log n) | O(n)            |

---

## Graphs (Space-Time Complexity)

| Algorithm               | Time Complexity    | Space Complexity |
|-------------------------|--------------------|-------------------|
| Breadth-First Search    | O(V + E)          | O(V)             |
| Depth-First Search      | O(V + E)          | O(V)             |
| A* Search               | O(E)              | O(V)             |
| Dijkstra’s Algorithm    | O(V²) / O(E log V)| O(V)             |

---

## Heaps (Space-Time Complexity)

| Operation       | Worst Case | Average Case | Best Case |
|-----------------|------------|--------------|-----------|
| Insert          | O(log n)   | O(log n)     | O(1)      |
| Delete          | O(log n)   | O(log n)     | O(1)      |
| Find Min/Max    | O(1)       | O(1)         | O(1)      |
| Search          | O(n)       | O(n)         | O(1)      |

