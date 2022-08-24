DS&A: Time Complexity - O(n) vs. O(log n)

# What is an Algorithm?

In computer programming terms, an algorithm is a set of well-defined instructions to solve a particular problem. It takes a set of input(s) and produces the desired output. For example,

An algorithm to add two numbers:

1.  Take two number inputs
2.  Add numbers using the + operator
3.  Display the result

## What are Data Structures?

Data structure is a storage that is used to store and organize data. It is a way of arranging data on a computer so that it can be accessed and updated efficiently.

Depending on your requirement and project, it is important to choose the right data structure for your project.

## Types of Data Structure

Basically, data structures are divided into two categories:

-   Linear data structure
-   Non-linear data structure

## Linear data structures

In linear data structures, the elements are arranged in sequence one after the other. Since elements are arranged in particular order, they are easy to implement.

However, when the complexity of the program increases, the linear data structures might not be the best choice because of operational complexities.

**Popular linear data structures are:**

### 1. Array Data Structure

### 2. Stack Data Structure

### 3. Queue Data Structure

### 4. Linked List Data Structure

## Non linear data structures

elements in non-linear data structures are not in any sequence. Instead they are arranged in a hierarchical manner where one element will be connected to one or more elements.

Non-linear data structures are further divided into graph and tree based data structures.

### 1. Graph Data Structure

In graph data structure, each node is called vertex and each vertex is connected to other vertices through edges.

![](media/686ce951d6afa49e2741344a7ae5cfcf.png)

**Popular Graph Based Data Structures:**

-   [Spanning Tree and Minimum Spanning Tree](https://www.programiz.com/dsa/spanning-tree-and-minimum-spanning-tree)
-   [Strongly Connected Components](https://www.programiz.com/dsa/strongly-connected-components)
-   [Adjacency Matrix](https://www.programiz.com/dsa/graph-adjacency-matrix)
-   [Adjacency List](https://www.programiz.com/dsa/graph-adjacency-list)

### 2. Trees Data Structure

a tree is also a collection of vertices and edges. However, in tree data structure, there can only be one edge between two vertices.

![](media/f2403c3493eac07c8d2ba8e3d00c112f.png)

**Popular Tree based Data Structure**

-   [Binary Tree](https://www.programiz.com/dsa/binary-tree)
-   [Binary Search Tree](https://www.programiz.com/dsa/binary-search-tree)
-   [AVL Tree](https://www.programiz.com/dsa/avl-tree)
-   [B-Tree](https://www.programiz.com/dsa/b-tree)
-   [B+ Tree](https://www.programiz.com/dsa/b-plus-tree)
-   [Red-Black Tree](https://www.programiz.com/dsa/red-black-tree)

To know more information [clickhere](https://www.programiz.com/dsa/data-structure-types)

**Algorithm Analysis**

Analysis of efficiency of an algorithm can be performed at two different stages, before implementation and after implementation, as

A priori analysis − This is defined as theoretical analysis of an algorithm. Efficiency of algorithm is measured by assuming that all other factors e.g. speed of processor, are constant and have no effect on implementation.

A posterior analysis − This is defined as empirical analysis of an algorithm. The chosen algorithm is implemented using programming language. Next the chosen algorithm is executed on target computer machine. In this analysis, actual statistics like running time and space needed are collected.

Algorithm analysis is dealt with the execution or running time of various operations involved. Running time of an operation can be defined as number of computer instructions executed per operation.

**Algorithm Complexity**

Suppose X is treated as an algorithm and N is treated as the size of input data, the time and space implemented by the Algorithm X are the two main factors which determine the efficiency of X.

Time Factor − The time is calculated or measured by counting the number of key operations such as comparisons in sorting algorithm.

Space Factor − The space is calculated or measured by counting the maximum memory space required by the algorithm.

The complexity of an algorithm f(N) provides the running time and / or storage space needed by the algorithm with respect of N as the size of input data.

**Space Complexity**

Space complexity of an algorithm represents the amount of memory space needed the algorithm in its life cycle.

Space needed by an algorithm is equal to the sum of the following two components

A fixed part that is a space required to store certain data and variables (i.e. simple variables and constants, program size etc.), that are not dependent of the size of the problem.

A variable part is a space required by variables, whose size is totally dependent on the size of the problem. For example, recursion stack space, dynamic memory allocation etc.

Space complexity S(p) of any algorithm p is S(p) = A + Sp(I) Where A is treated as the fixed part and S(I) is treated as the variable part of the algorithm which depends on instance characteristic I. Following is a simple example that tries to explain the concept

Algorithm

SUM(P, Q)

Step 1 - START

Step 2 - R ← P + Q + 10

Step 3 - Stop

Here we have three variables P, Q and R and one constant. Hence S(p) = 1+3. Now space is dependent on data types of given constant types and variables and it will be multiplied accordingly.

**Time Complexity**

Time Complexity of an algorithm is the representation of the amount of time required by the algorithm to execute to completion. Time requirements can be denoted or defined as a numerical function t(N), where t(N) can be measured as the number of steps, provided each step takes constant time.

For example, in case of addition of two n-bit integers, N steps are taken. Consequently, the total computational time is t(N) = c\*n, where c is the time consumed for addition of two bits. Here, we observe that t(N) grows linearly as input size increases

https://www.tutorialspoint.com/time-and-space-complexity-in-data-structure

https://www.javatpoint.com/linear-search
