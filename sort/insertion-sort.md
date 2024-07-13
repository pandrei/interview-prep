```
function insertionSort(array) {
  for i from 1 to length(array) - 1 {
    key = array[i]
    j = i - 1
    // Move elements of array[0..i-1] that are greater than key
    // to one position ahead of their current position
    while j >= 0 and array[j] > key {
      array[j + 1] = array[j]
      j = j - 1
    }
    array[j + 1] = key
  }
}
```