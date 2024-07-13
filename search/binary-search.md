```
function binarySearch(array, value, left, right) {
  if (left > right) { // exit condition
    return -1;
  }
  mid = left + (right - left) // 2;
  if (array[mid] == value) {
    return mid;
  } else if (array[mid] < value) {
    return binarySearch(array, value, mid + 1, right);
  } else {
    return binarySearch(array, value, left, mid - 1);
  }
}
```