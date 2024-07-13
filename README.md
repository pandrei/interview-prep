# Algorithms relevant for interviews

## Sorting Algorithms
- Quick Sort - A divide-and-conquer algorithm that selects a pivot and partitions the array around the pivot.
- Merge Sort - A divide-and-conquer algorithm that divides the array into halves, sorts them, and then merges them back together.
- Bubble Sort - A simple comparison-based algorithm that repeatedly steps through the list, compares adjacent elements and swaps them if they are in the wrong order.
- Insertion Sort - Builds the final sorted array one item at a time by repeatedly inserting the next element into the correct position.
- Selection Sort - Divides the input list into two parts: a sorted and an unsorted part, then repeatedly selects the smallest element from the unsorted part and moves it to the sorted part.
- Heap Sort - Converts the array into a heap structure, then repeatedly extracts the maximum element from the heap and rebuilds the heap.

## Searching Algorithms
- Binary Search - Efficiently searches a sorted array by repeatedly dividing the search interval in half.
- Depth-First Search (DFS) - Explores as far as possible along each branch before backtracking.
- Breadth-First Search (BFS) - Explores all neighbors at the present depth before moving on to nodes at the next depth level.

## Graph Algorithms
- Dijkstra's Algorithm - Finds the shortest paths from a source vertex to all other vertices in a weighted graph.
- Bellman-Ford Algorithm - Computes shortest paths from a single source vertex to all other vertices, even with negative weights.
- Floyd-Warshall Algorithm - Finds shortest paths between all pairs of vertices in a weighted graph.
- Kruskal's Algorithm - Finds the minimum spanning tree of a graph by sorting edges and adding them one by one.
- Prim's Algorithm - Builds the minimum spanning tree by starting with a single vertex and adding the cheapest edge from the tree to a new vertex.
- A* Search Algorithm - Finds the shortest path between nodes in a graph, using heuristics to improve efficiency.

## Dynamic Programming Algorithms
- Fibonacci Sequence - Computes the nth Fibonacci number using memoization or tabulation.
- Longest Common Subsequence (LCS) - Finds the longest subsequence common to two sequences.
- Longest Increasing Subsequence (LIS) - Finds the longest increasing subsequence in an array.
- 0/1 Knapsack Problem - Determines the most valuable combination of items that can be put in a knapsack of fixed capacity.
- Edit Distance (Levenshtein Distance) - Measures the similarity between two strings by calculating the minimum number of operations needed to transform one string into the other.


## Greedy Algorithms
- Activity Selection - Selects the maximum number of activities that don't overlap.
- Huffman Coding - Constructs an optimal prefix code based on the frequencies of symbols.
- Fractional Knapsack Problem - Maximizes the total value in the knapsack by allowing fractions of items.


## String Algorithms
- KMP Algorithm - Searches for occurrences of a word within a text using a pattern.
- Rabin-Karp Algorithm - Searches for a substring using a rolling hash.
- Trie - A tree-like data structure that stores a dynamic set of strings, often used for autocomplete and spell-checking.


## Mathematical Algorithms
- Euclidean Algorithm - Computes the greatest common divisor (GCD) of two integers.
- Sieve of Eratosthenes - Finds all prime numbers up to a given limit.
- Fast Exponentiation - Computes powers of a number efficiently using divide-and-conquer.

## Miscellaneous Algorithms
- Topological Sort - Orders the vertices of a directed acyclic graph (DAG) such that for every directed edge 
- 𝑢→𝑣u→v, vertex 𝑢u comes before 𝑣v.
- Union-Find (Disjoint Set) - Manages a partition of a set into disjoint subsets, supports union and find operations.
- Reservoir Sampling - Randomly selects a sample of 𝑘k items from a population of unknown size.