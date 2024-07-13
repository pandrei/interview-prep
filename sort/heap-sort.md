# Heap Sort

Building the max-heap takes `O(n)` time.

The idea is to convert the unsorted array into a max-heap. Since a heap is binary, the index of the last non-leaf node is `n / 2 - 1`.

### Time complexity

Each heapify operation takes `O(log ⁡n)` time, and we perform `n` such operations, so the total time complexity is `O(n log⁡ n)`.

### Space complexity

Usually done in-place, so constant.

### Advantages

- **Efficiency**: Heap Sort has a guaranteed worst-case time complexity of O(nlog⁡n)O(n \log n)O(nlogn).
- **Memory Usage**: It is an in-place algorithm with O(1)O(1)O(1) extra space.

### Disadvantages

- **Not Stable**: It does not maintain the relative order of equal elements.
- **Cache Performance**: It has poor cache performance due to its non-linear memory access patterns.

## Pseudocode

```
function heapSort(array) {
  n = length(array)

  // Build a max-heap
  for i from n / 2 - 1 down to 0 {
    heapify(array, n, i)
  }

  // Extract elements from the heap one by one
  for i from n - 1 down to 1 {
    // Move current root to the end
    swap(array, 0, i)

    // Call heapify on the reduced heap
    heapify(array, i, 0)
  }
}

function heapify(array, n, i) {
  largest = i  // Initialize largest as root
  left = 2 * i + 1  // Left child
  right = 2 * i + 2  // Right child

  // If left child is larger than root
  if left < n and array[left] > array[largest] {
    largest = left
  }

  // If right child is larger than largest so far
  if right < n and array[right] > array[largest] {
    largest = right
  }

  // If largest is not root
  if largest != i {
    swap(array, i, largest)

    // Recursively heapify the affected sub-tree
    heapify(array, n, largest)
  }
}

function swap(array, i, j) {
  temp = array[i]
  array[i] = array[j]
  array[j] = temp
}

```





## Java implementation

```
public static void heapSort(int[] array) {
    int n = array.length;

    // Build a max-heap
    for (int i = n / 2 - 1; i >= 0; i--) {
        heapify(array, n, i);
    }

    // Extract elements from the heap one by one
    for (int i = n - 1; i > 0; i--) {
        // Move current root to the end
        swap(array, 0, i);

        // Call heapify on the reduced heap
        heapify(array, i, 0);
    }
}

private static void heapify(int[] array, int n, int i) {
    int largest = i; // Initialize largest as root
    int left = 2 * i + 1; // Left child
    int right = 2 * i + 2; // Right child

    // If left child is larger than root
    if (left < n && array[left] > array[largest]) {
        largest = left;
    }

    // If right child is larger than largest so far
    if (right < n && array[right] > array[largest]) {
        largest = right;
    }

    // If largest is not root
    if (largest != i) {
        swap(array, i, largest);

        // Recursively heapify the affected sub-tree
        heapify(array, n, largest);
    }
}

private static void swap(int[] array, int i, int j) {
    int temp = array[i];
    array[i] = array[j];
    array[j] = temp;
}
```

