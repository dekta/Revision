# Data structure and Algorithm

## Data Structure
- In computer science, a data structure is a way of organizing, storing, and manipulating data in a computer so that it can be used efficiently. It provides a way to manage and organize data in a specific way so that it can be easily accessed and modified. Data structures can be implemented using programming languages and can be used for a variety of purposes, including searching, sorting, and indexing data. Some common examples of data structures include arrays, linked lists, stacks, queues, trees, and graphs.

## Algorithm
- An algorithm is a set of instructions or a procedure for solving a problem or performing a specific task. It is a sequence of well-defined steps or rules that describe how to perform a computation or solve a problem. Algorithms are used in programming and computer science to design software systems and solve complex computational problems. A good algorithm is efficient, accurate, and solves the problem in the most optimal way possible.


| s.n. | Data Structure(in-built) | Data Structure(not in-built)  | Alogorithm | Techniques |
| :----: | :---------------------: | :---------------------------: | :--------: | :---------: |
| 1     | Array                   |     Stack                     | Sliding window | Backtracking: N-Queens Problem,Subset Sum Problem,Sudoku Solver |
| 2     | Object                  |Queue                          | Two pointer  | recursion => is a technique used in algorithms to solve problems |
| 3     | set                     | Linked List                   |  Searching Algorithms=> Linear Search, Binary Search  |         |
| 4     |                         | Tree  | Sorting Algorithms: Bubble Sort,Selection Sort,Insertion Sort,Merge Sort,Quick Sort |     |
| 5 |   | Graph | Graph Algorithms=>Depth-First Search (DFS),Breadth-First Search (BFS),Dijkstra's Algorithm,Bellman-Ford Algorithm,Floyd-Warshall Algorithm | |
| 6 |     | Hash Table  | Greedy Algorithms: Coin Change Problem,Fractional Knapsack Problem,Activity Selection Problem |  |
| 7 |       |       |  | Dynamic Programming:Fibonacci Series,Knapsack Problem,Longest CommoSubsequence,Longest Increasing Subsequence |
| 8 |       |       |  | | |
 9 |        |       |   | | |



 ### Array

- In JavaScript, an array is a data structure that stores a collection of elements, such as numbers or strings, in a single variable. Arrays are one of the most commonly used data types in JavaScript and are frequently used to store lists of data.
- You can access the elements of an array by their index, which is a numerical value that represents their position in the array. In JavaScript, array indices start at 0, so the first element of an array is at index 0, the second element is at index 1, and so on.
- var myArray = [element1, element2, ..., elementN];
- time complexity

| Method |  Average case | worst case | use |
| :-----: | :--------: | :---------: | :---: |
| Accessing an element by index | O(1) | O(1)  | |
| Searching for an element | O(n) | O(n) | |
| Adding an element to the end of the array | O(1) |  O(n) | |
| Adding an element to the beginning or middle of the array | O(n) | O(n) | |
| Removing an element from the end of the array |O(1) | O(1)| |
| Removing an element from the beginning or middle of the array |  O(n) | O(n) | |
| toString() | O(n) | O(n)  |  convert a number to string |
| join()  |  O(n)  | O(n)   |  joins all array elements into a string. |
|   pop() |  O(1)   | O(1)   | Removes the last element from an array | 
|   push()  |  O(1)   |  O(1)   | adds a new element to an array (at the end) |
| shift()    |   O(n)   |  O(n)   |  removes the first array element and "shifts" all other elements to a lower index | 
| unshift() |  O(n)   |  O(n)  | adds a new element to an array (at the beginning), and "unshifts" older elements | 
| length  |   O(1)  |  O(1)   | give the length of array |
| delete |  O(n) |  O(n)  | Array elements can be deleted using the JavaScript operator |
| concat() | O(n)  | O(n) | creates a new array by merging (concatenating) existing arrays |
| splice() | O(n) | O(n)  | method can be used to add new items to an array , you can use splice() to remove elements without leaving "holes" in the array ,method does not remove any elements from the source array.|
| slice() | O(n) | O(n) | method slices out a piece of an array into a new array. , method creates a new array |
| sort() |  O(n log n) |  | sort the array  |
| reverse() | O(n)  |  |   reverse the array |


### Object

- In JavaScript, an object is a data structure that allows you to store collections of key-value pairs. Each key in the object is a unique string that is used to access its corresponding value.
- var myObject = {key1: value1, key2: value2, ..., keyN: valueN}; 
- In addition to storing simple values like strings and numbers, objects can also contain functions, other objects, and arrays. This makes them a powerful tool for organizing and storing complex data structures in JavaScript.



### Set
- In JavaScript, a Set is a built-in object that represents a collection of unique values. You can use a Set to store and manipulate data in a way that ensures that each value is unique, and to easily perform operations like union, intersection, and difference between multiple sets.
- const mySet = new Set();
- const mySet = new Set([value1, value2, ..., valueN]);
- mySet.add(value);
- mySet.delete(value);
- mySet.has(value); // returns true if the value exists, false otherwise
- mySet.size; // returns the number of elements in the Set
- The order of values in a Set is determined by their insertion order. A Set only contains unique values, so if you try to add a value that already exists in the Set, it will be ignored.
- Add or remove element: O(1)
- Check if element exists: O(1)



### Stack
- a stack is an abstract data type that represents a collection of elements with two principal operations: push, which adds an element to the collection, and pop, which removes the most recently added element that was not yet removed. The order in which elements are removed from a stack is known as Last-In-First-Out (LIFO).
- A stack is typically implemented using an array or a linked list, where elements are added and removed from the same end of the data structure. The end of the stack where elements are added is called the "top" of the stack.
- Some of the common operations performed on a stack include:
    - Push: This operation adds an element to the top of the stack.
    - Pop: This operation removes the top element from the stack.
    - Peek: This operation returns the top element of the stack without removing it.
    - IsEmpty: This operation checks if the stack is empty or not.
    - Size: This operation returns the number of elements in the stack.
- The space complexity of a stack is also O(n), where n is the number of elements in the stack. This is because a stack is a linear data structure that stores elements in a contiguous block of memory.
- Example: A web browser uses a stack to keep track of the user's navigation history. Each time the user visits a new page, the page is pushed onto a stack. If the user clicks the back button, the most recent page is popped off the stack and displayed.
- Push element: O(1)
- Pop element: O(1)
- Peek element: O(1)
- Access or modify element at arbitrary index: O(1)
- Check if element exists: O(n)



| Abstract Data type |
| :-----------------:
| An abstract data type (ADT) is a way of describing a type of data and the operations that can be performed on it, without specifying exactly how those operations are implemented. It's like a blueprint for creating different kinds of data structures that have a set of behaviors and functions that can be used to manipulate them, without revealing the details of how they work behind the scenes. For example, a stack is an abstract data type that allows you to add and remove elements in a specific order, but how those elements are actually stored and accessed is hidden from the user. Some examples of abstract data types include stacks, queues, lists, trees, and graphs. Each of these data types has a set of operations that can be performed on them, such as adding an element, removing an element, or searching for an element.




### Queue
- In JavaScript, a queue data structure is used to store and manage a collection of elements in a first-in-first-out (FIFO) order. It can be implemented using arrays or linked lists.
- The time complexity of the queue operations is as follows:
    - enqueue: O(1)
    - dequeue: O(1)
    - front: O(1)
    - isEmpty: O(1)
- The space complexity of the queue depends on the number of elements it stores at any given time
- A Queue is a linear data structure that follows the FIFO (First In First Out) principle. This means that the first element that is inserted into the Queue is the first one to be removed. A Queue has two main operations: Enqueue and dequeue
- enqueue adds an element to the end of the array using the push method, and dequeue removes an element from the front of the array using the shift method. peek returns the first element in the array without removing it, and size returns the length of the array.
- Example: Call Center Queue: In a call center, calls are typically handled in the order that they are received. Calls are placed into a queue, and the next available operator will take the next call in the queue.



### LinkedList
- In JavaScript, linked lists can be implemented using objects as nodes and storing the reference to the next node as a property of the node object.
- A linked list is a data structure consisting of a group of nodes, each of which contains a reference to the next node in the sequence. In a singly linked list, each node only has a reference to the next node, while in a doubly linked list, each node has references to both the next and previous nodes.
- The time complexity of adding or removing a node from a linked list is O(n), where n is the number of nodes in the list, since we may need to traverse the entire list to find the node to add or remove. However, inserting or removing a node at the beginning of the list can be done in constant time, since we only need to update the head reference. The space complexity of a linked list is O(n), since we need to allocate memory for each node.
- Example : Implementing a stack or queue: A linked list can be used to implement a stack or queue data structure. In this case, the linked list can be used to store the elements of the stack or queue, with the first element of the list representing the top of the stack or front of the queue.
- Add or remove element given pointer before add/removal location:O(n)
- Add or remove element given pointer at add/removal location:O(1) if doubly linked
- Add or remove element at arbitrary position without pointer: O(n)
- Access element at arbitrary position without pointer: O(n)
- Check if element exists: O(n)
- Reverse between position i and j: O(j−i)
- Detect a cycle: O(n) using fast-slow pointers or hash map

### Tree 
- A tree data structure is a hierarchical structure consisting of nodes connected by edges or links. It is similar to a real-life tree, where each node is like a branch connected to the trunk, and the edges represent the connection between the nodes.
- In a tree, there is always one node called the "root" node, which is at the top of the hierarchy. All other nodes are connected to this root node through edges. The nodes that have other nodes connected to them are called "parent" nodes, and the nodes that are connected to them are called "child" nodes.
- The tree structure is commonly used in computer science for representing hierarchical data, such as file directories, organization charts, or the structure of an XML or HTML document.
- Example:  organization of files and folders in a computer's file system. Each folder can contain multiple subfolders, and each subfolder can contain multiple files and subfolders, forming a tree-like structure.


### Graph
- a graph data structure is a way to represent a set of objects (nodes or vertices) that are connected by links (edges or arcs). Graphs can be used to model a wide variety of real-world problems, such as social networks, transportation systems, and computer networks.
- In a graph, each node represents a specific object, and the edges between nodes represent relationships between those objects. For example, in a social network graph, each node might represent a person, and the edges might represent friendships between those people.



### Hash Table
- A hash table, also known as a hash map, is a data structure that stores data in an associative manner, using key-value pairs. The keys are hashed to a numeric index, which is used to access the corresponding value in the table.
- In JavaScript, hash tables can be implemented using objects, which are essentially collections of key-value pairs. When a new key-value pair is added to the hash table, the key is hashed using a hash function and the resulting index is used to store the value in the object. When retrieving a value, the hash function is used to calculate the index and the value is retrieved from the corresponding location in the object.
- Hash tables are commonly used to implement caches, databases, and other data structures that require fast key-based lookups. They have a time complexity of O(1) for average case operations, making them efficient for use in many scenarios. However, in the worst case, hash tables can have a time complexity of O(n), where n is the number of elements in the table, if there are many hash collisions. Therefore, it's important to choose an appropriate hash function to minimize the chances of collisions.
- Add or remove key-value pair: O(1)
- Check if key exists: O(1)
- Check if value exists: O(n)
- Access or modify value associated with key: O(1)
- Iterate over all keys, values, or both: O(n)




## Algorithm

## Sliding window 
- Sliding window algorithm is a technique used to solve problems where we need to find a substring or a subarray satisfying certain constraints. It works by creating a window of size k and sliding it over the input string or array from left to right.
- The algorithm maintains two pointers - left and right. The left pointer points to the start of the window, while the right pointer points to the end of the window. The size of the window is fixed and is equal to k. At each step, the window slides one position to the right.
- The time complexity of sliding window algorithm is O(n), where n is the length of the input string or array.
- In general, the space complexity of the sliding window algorithm is O(k), where k is the size of the sliding window. This is because the algorithm only needs to store k elements at any given time.




## Two pointer
- The Two Pointer Algorithm is a technique used to solve problems related to arrays or linked lists. The idea behind this algorithm is to use two pointers that traverse the data structure in some fashion, often simultaneously, until they identify some combination of elements that meet a certain condition.
- Two pointer algorithm is a technique used in computer programming to solve problems involving arrays or linked lists. It involves using two pointers that move through the data structure at different speeds to solve a problem more efficiently. The two pointers can move in different directions or at different speeds depending on the problem. This algorithm is often used for problems that involve searching for a target value, finding a substring, or checking for the existence of a palindrome. The basic idea behind this algorithm is to maintain two pointers, which point to two different positions in the data structure, and move them to get closer to the solution.
- The space complexity of the Two Pointer Algorithm is generally O(1), as it only requires a constant amount of extra memory to store the two pointers. The time complexity of the algorithm varies depending on the specific use case, but it is typically O(n), as both pointers traverse the data structure only once.




## Linear Search
- Linear Search is a simple search algorithm that is used to find an element in a list or an array. It works by sequentially checking each element of the list or array until the desired element is found or the end of the list is reached.
- The time complexity of linear search is O(n), where n is the number of elements in the list or array. This means that the worst-case scenario is when the target value is not in the list and the algorithm has to check every element in the list. The space complexity of linear search is O(1), since it only requires a constant amount of memory to store the loop index and the target value.



## Binary search 
- Binary search is a search algorithm used to find the position of a specific value (key) within a sorted array. The algorithm works by repeatedly dividing the sorted array into two equal halves and searching for the key within the appropriate half until the key is found or it is determined that the key does not exist in the array.
- Here's how the binary search algorithm works:
    - Start by finding the middle element of the array.
    - If the middle element is equal to the key, then we have found the position of the key in the array.
    - If the middle element is less than the key, then the key must be in the right half of the array. So, we repeat the search on the right half of the array.
    - If the middle element is greater than the key, then the key must be in the left half of the array. So, we repeat the search on the left half of the array.
    - We continue this process until we find the key or determine that it does not exist in the array.
- The time complexity of binary search algorithm is O(log n), where n is the number of elements in the array.


## Bubble Sort
- Bubble Sort is a simple sorting algorithm that repeatedly steps through the list, compares adjacent elements and swaps them if they are in the wrong order. The pass through the list is repeated until the list is sorted.
- The algorithm works by comparing each pair of adjacent elements in the list from the beginning, swapping them if they are in the wrong order (ascending or descending arrangement) and continuing until the end of the list.
- The time complexity of the Bubble Sort algorithm is O(n^2) in the worst and average cases, and O(n) in the best case (when the list is already sorted). The space complexity is O(1) as the algorithm only requires a constant amount of additional space for the swapping of elements.



## knapsack
- The Knapsack problem is a combinatorial optimization problem where you have to select a set of items, each with a weight and a value, in such a way that the total weight is less than or equal to a given limit and the total value is maximized.
- The algorithm for solving the Knapsack problem is the dynamic programming approach. It involves building a table where each cell (i, j) represents the maximum value that can be obtained by selecting from the first i items, subject to a weight limit of j.
- The Knapsack problem is a classic optimization problem in computer science. It involves choosing items to put in a knapsack (a backpack or a container) that has a limited capacity, with the goal of maximizing the total value of the items.
- Here's the general outline of the algorithm:
    - Create a table with (n+1) rows and (W+1) columns, where n is the number of items and W is the weight limit.
    - Initialize the first row and the first column to 0.
    - For each item i from 1 to n:
        - a. For each weight limit j from 1 to W:
        i. If the weight of the item i is greater than j, set the value of the cell (i, j) to the value of the cell (i-1, j).
        ii. Otherwise, set the value of the cell (i, j) to the maximum of the following two values:
        1. The value of the cell (i-1, j).
        2. The value of the current item i plus the value of the cell (i-1, j-weight[i]), where weight[i] is the weight of item i.
    - The maximum value that can be obtained is in the cell (n, W).
- The time complexity of this algorithm is O(nW), where n is the number of items and W is the weight limit. The space complexity is also O(nW), as we are creating a table with (n+1) rows and (W+1) columns.

- In other words, imagine you are a thief and you are trying to steal the most valuable items from a store, but you can only carry a limited amount of weight in your bag. You want to choose the items that have the highest value-to-weight ratio so that you can maximize the total value of the items you steal without going over the weight limit of your bag.
- The Knapsack problem is commonly used in computer science to test the efficiency of algorithms, particularly dynamic programming and greedy algorithms.


## Selection Sort
- Selection Sort is a sorting algorithm that works by repeatedly finding the minimum element from the unsorted part of an array and placing it at the beginning of the array. It divides the input array into two parts: the sorted part and the unsorted part.
- Here are the steps of the Selection Sort algorithm:
    - Set the first element of the array as the minimum value.
    - Traverse the array starting from the second element, and for each element, compare it with the minimum value. If the element is smaller than the minimum value, set it as the new minimum value.
    - After reaching the end of the array, swap the minimum value with the first element of the array.
    - Repeat the above steps for the remaining unsorted part of the array, i.e., from the second element to the end of the array.
- The time complexity of the Selection Sort algorithm is O(n^2), where n is the number of elements in the array. This is because the algorithm needs to traverse the array twice for each element. The space complexity is O(1), as the algorithm sorts the array in place without requiring extra memory.



## Merge Sort
- Merge Sort is a sorting algorithm that follows the divide-and-conquer approach. It breaks down the input array into smaller subarrays, sorts them recursively, and then merges them to get the final sorted array. The algorithm has a time complexity of O(n log n).
- Here are the steps to perform the Merge Sort algorithm:
   -  Divide the array into two halves, by finding the middle index.
   -  Recursively sort the two halves using merge sort.
   -  Merge the two sorted halves by comparing the elements from each half and placing them in order in a new array.
   -  Repeat the merging process until all subarrays have been merged into one final sorted array.


## quick sort
- Quick sort is a sorting algorithm that uses the divide-and-conquer approach. It works by partitioning an array into two sub-arrays, sorting the sub-arrays independently, and then combining them in a way that results in a sorted array.
- The basic idea behind quick sort is to select a pivot element, which can be any element in the array. Then, we partition the array into two sub-arrays, one with elements smaller than the pivot and one with elements greater than the pivot. We then recursively apply the same process to each sub-array until the entire array is sorted.
- Here are the steps of the quick sort algorithm:
    - Choose a pivot element from the array.
    - Partition the array into two sub-arrays, one with elements smaller than the pivot and one with elements greater than the pivot.
    - Recursively apply the same process to each sub-array.
    - Combine the sorted sub-arrays to obtain the final sorted array.
- The time complexity of the quick sort algorithm is O(n log n) in the average case and O(n^2) in the worst case (when the pivot is chosen poorly and the array is already sorted or almost sorted). However, in practice, quick sort is often faster than other sorting algorithms due to its cache efficiency and ability to be easily parallelized.



## Dynamic Programming
- Dynamic Programming is a problem-solving technique used in computer science and mathematics. It involves breaking down a complex problem into smaller sub-problems and solving them in a systematic way, building up to the solution of the original problem. The approach involves storing the solutions of sub-problems in memory so that they can be accessed and reused as needed. Dynamic Programming is used to solve a wide range of problems, including optimization, sequence analysis, and graph algorithms. It is particularly useful for problems that involve overlapping sub-problems, where the same sub-problem may need to be solved multiple times.
- In JavaScript, dynamic programming can be used to solve a variety of problems, such as finding the maximum subarray, the longest common subsequence, or the shortest path in a graph.
- The time complexity of a DP algorithm can be represented by O(n*m), where n is the size of the input and m is the number of subproblems.


## backtracking
- Backtracking is a problem-solving technique used in algorithm design. It involves building solutions to problems incrementally, and at each step, making a decision that can lead to either a successful or an unsuccessful outcome. If the current decision leads to a dead end, the algorithm backtracks, undoing the last decision, and tries an alternative path.
- The process continues until all possible solutions have been explored or a satisfactory solution is found. Backtracking is particularly useful when searching for all possible solutions to a problem, as it allows the algorithm to eliminate unpromising paths early on and explore more promising ones. It is commonly used in problems such as puzzle-solving, permutation generation,graph traversal,Sudoku puzzles, or finding the shortest path in a graph.
- The time complexity of a backtracking algorithm can be represented by O(b^d), where b is the branching factor, i.e., the number of choices at each decision point, and d is the depth of the search tree.



## recursion
- Recursion is a programming technique that allows a function to call itself within its own code. In simpler terms, recursion is a process in which a function solves a problem by breaking it down into smaller subproblems, solving each subproblem recursively, and then combining the results to solve the original problem.
- This means that the time taken by the function is proportional to the input size n. In general, the time complexity of a recursive function can range from O(1) to O(2^n), depending on the number of recursive calls made and the time complexity of each call.



## greedy algorithm
- Greedy algorithms are a class of algorithms that aim to find the optimal solution for a problem by making a locally optimal choice at each step. The idea is to make a decision based on the best available option at the moment without considering the future consequences. Greedy algorithms are usually used for optimization problems, where the goal is to find the best solution among the possible choices.
- A simple example of a greedy algorithm is the coin change problem. In this problem, we are given a set of coins of different denominations and a target amount. The goal is to find the minimum number of coins required to make up the target amount. A greedy approach to solving this problem is to always choose the largest denomination coin that fits into the remaining amount until the amount is zero.
- The time complexity of a greedy algorithm depends on the problem and the implementation. In some cases, greedy algorithms can solve problems in linear time, while in other cases, they may require exponential time. It is important to note that greedy algorithms do not always provide the optimal solution for a problem, and in some cases, a more complex approach may be required.







