```
function quickSort(array, left, right) {
  if (left < right) {
    pivotIndex = partition(array, left, right)
    quickSort(array, left, pivotIndex - 1)
    quickSort(array, pivotIndex + 1, right)
  }
}

function partition(array, left, right) {
  pivot = array[right]
  i = left - 1
  for j = left to right - 1 {
    if array[j] <= pivot {
      i = i + 1
      swap(array, i, j)
    }
  }
  swap(array, i + 1, right)
  return i + 1
}

function swap(array, i, j) {
  temp = array[i]
  array[i] = array[j]
  array[j] = temp
}
```