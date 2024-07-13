# Depth-first Search (DFS)

As it's name says, the DFS starts with a path, and explores it until it can no longer advance before back-tracking.

While DFS is typically used to search for something, it can also be a mean of iterating over a set of data.

## Pseudocode

```
DFS(source, target) {
  initialize empty stack
  initialize set for visited nodes
  
  push source to stack
  
  while stack is not empty {
    current = pop stack
    if current is target {
      return true
    }
    if current is not in visited {
      mark current as visited
      for every neighbor of current {
        push neighbor to stack
      }
    }
  }
  return false
}
```

## Step - by - step

Consider the graph below

![graph](graph.png)

Let our source be A.

- Move to node B (pushing B onto the stack).
- From B, move to D (pushing D onto the stack).
- Node D has no unvisited neighbors, so pop D.
- Backtrack to B, move to E (pushing E onto the stack).
- Node E has no unvisited neighbors, so pop E.
- Backtrack to B, all neighbors of B are visited, so pop B.
- Backtrack to A, move to C (pushing C onto the stack).
- From C, move to F (pushing F onto the stack).
- Node F has no unvisited neighbors, so pop F.
- Backtrack to C, all neighbors of C are visited, so pop C.
- Backtrack to A, all neighbors of A are visited, so pop A.

Our exploration path is A - B - D - B - E - B - A - C - F



### Time Complexity

- O(V + E) Where V is the number of vertices and  E is the number of edges in the graph.
  - In the worst case, DFS visits all vertices and edges. For each vertex, it checks all adjacent vertices (edges).

### Space Complexity

- O(V) The space complexity is primarily due to the stack used for recursion or an explicit stack data structure. In addition, space is needed for storing the visited nodes.
  - In the worst case, the recursion stack can go as deep as the number of vertices in the graph.

### Advantages of DFS

1. **Memory Efficient**:
   - Uses less memory compared to Breadth-First Search (BFS) because it only needs to store a single path from the root to a leaf, along with the unvisited nodes.
2. **Path Finding**:
   - Good for finding a path between two nodes in an unweighted graph, as it explores as far as possible along each branch before backtracking.
3. **Cycle Detection**:
   - Can be used to detect cycles in a graph by checking back edges in the recursive call stack.
4. **Topological Sorting**:
   - Useful for topological sorting in directed acyclic graphs (DAGs).
5. **Connected Components**:
   - Can help in finding connected components in a graph.

### Disadvantages of DFS

1. **May Not Find Shortest Path**:
   - Unlike BFS, DFS does not necessarily find the shortest path to a target node in an unweighted graph.
2. **Can Get Stuck in Deep Paths**:
   - DFS can go deep into a path with many nodes before backtracking, which might not be efficient if the target node is located on a shallower path.
3. **Requires More Stack Space**:
   - The depth of the recursion stack can be problematic for very deep or infinite graphs, leading to stack overflow issues.
4. **Not Always Optimal for Large Graphs**:
   - For very large graphs, the memory used by the stack can be significant, and DFS might not be the best choice compared to iterative algorithms that use less memory.

## Java implementations

Using a Node object

```
    public static void dfs(Node node) {
        if (node == null) return;

        node.visited = true;
        System.out.print(node.value + " ");

        for (Node neighbor : node.neighbors) {
            if (!neighbor.visited) {
                dfs(neighbor);
            }
        }
    }
```

Using an adjacency matrix

```
    public static void dfs(int[][] graph, int startNode) {
        int numNodes = graph.length;
        boolean[] visited = new boolean[numNodes];
        Stack<Integer> stack = new Stack<>();

        stack.push(startNode);

        while (!stack.isEmpty()) {
            int node = stack.pop();

            if (!visited[node]) {
                visited[node] = true;
                for (int i = numNodes - 1; i >= 0; i--) { // reverse order for stack behavior
                    if (graph[node][i] == 1 && !visited[i]) {
                        stack.push(i);
                    }
                }
            }
        }
    }
```

