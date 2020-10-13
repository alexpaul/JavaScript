# Algorithms 

## Binary Search

```javascript 
function binarySearch(arr, target) {
  let low = 0; 
  let high = arr.length; 
  while (low < high) {
    const middleIndex = Math.floor(low + (high - low) / 2); 
    if (arr[middleIndex] == target) {
      return middleIndex; 
    } else if (arr[middleIndex] > target) { // look left
      high = middleIndex; 
    } else { // look right
      low = middleIndex + 1; 
    }
  }
  return -1; 
}

const result = binarySearch([1, 2, 3, 4, 5], 3); 
console.log(result); // index 2 is returned
```
