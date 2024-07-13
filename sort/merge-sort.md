```
function mergeSort(array, left, right) {
  if left < right {
    middle = left + (right - left) // 2
    mergeSort(array, left, middle)
    mergeSort(array, middle + 1, right)
    merge(array, left, middle, right)
  }
}

function merge(array, left, middle, right) {
  // Create temporary arrays for left and right subarrays
  n1 = middle - left + 1
  n2 = right - middle
  leftArray = new array of size n1
  rightArray = new array of size n2

  // Copy data to temporary arrays leftArray and rightArray
  for i from 0 to n1 - 1 {
    leftArray[i] = array[left + i]
  }
  for j from 0 to n2 - 1 {
    rightArray[j] = array[middle + 1 + j]
  }

  // Merge the temporary arrays back into the original array
  i = 0 // Initial index of leftArray
  j = 0 // Initial index of rightArray
  k = left // Initial index of merged subarray

  while i < n1 and j < n2 {
    if leftArray[i] <= rightArray[j] {
      array[k] = leftArray[i]
      i = i + 1
    } else {
      array[k] = rightArray[j]
      j = j + 1
    }
    k = k + 1
  }

  // Copy any remaining elements of leftArray, if any
  while i < n1 {
    array[k] = leftArray[i]
    i = i + 1
    k = k + 1
  }

  // Copy any remaining elements of rightArray, if any
  while j < n2 {
    array[k] = rightArray[j]
    j = j + 1
    k = k + 1
  }
}
```