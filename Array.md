# Array 

```javascript 
let arrayLength = 5
let arr1 = []; 
let arr2 = Array(arrayLength); // using Array object
```

## `length`

```javascript 
console.log(arr1.length); 
console.log(arr2.length); 
```

## Adding data during execution 

```javascript 
let arr3 = ['A', true, 2]; 
console.log(arr3[0]); 
console.log(arr3[1]); 
```

## Adding data after execution 

```javascript 
arrayLength = 2; 
let arr4 = Array(arrayLength); 
arr4[0] = 'Value at index 0'; 
console.log(arr4[0]); 
console.log(arr4[1]) // undefined - no value added here 
```

## length and index 

```javascript 
let arr5 = Array(3); 
arr5[2] = 'Adding a value'; 
console.log(arr5[2]); 
console.log(arr5[arr5.length - 1]); 
console.log(arr5[0]); // no value yet 
console.log(arr5[1]); // no value yet 
```

## `push()` and `pop()`

```javascript 
let fellows = ['Gabe', 'Fred', 'Mary']; 
fellows.push('Tim'); 
console.log(fellows); // [ 'Gabe', 'Fred', 'Mary', 'Tim' ]
console.log(`The length of fellows is ${fellows.length}`); // 4 
console.log(fellows.pop()) // Tim
console.log(fellows); 
```

## `shift()` and `unshift()`

```javascript 
console.log(fellows.unshift('Esther')); // add new value to the front of the array
console.log(fellows); // [ 'Esther', 'Gabe', 'Fred', 'Mary' ]
console.log(fellows.shift()); // remove first value
console.log(fellows); // [ 'Gabe', 'Fred', 'Mary' ]
```

## `concat`

```javascript 
let foodOptions = ['Thai', 'Seafood', 'Pasta'];
let otherFoodOptions = ['Tacos', 'Falafel'];
let allFoodOptions = foodOptions.concat(otherFoodOptions); 
console.log(`All the food options ${allFoodOptions}`);
// All the food options Thai,Seafood,Pasta,Tacos,Falafel
```

## Challenges 

#### Challenge 1

Write a `range` function that takes two arguments, start and end, and returns an array containing all the numbers from start up to (and including) end.

Next, write a `sum` function that takes an array of numbers and returns the sum of these numbers. Run the example program and see whether it does indeed return 55.

As a bonus assignment, modify your range function to take an optional third argument that indicates the “step” value used when building the array. If no step is given, the elements go up by increments of one, corresponding to the old behavior. The function call range(1, 10, 2) should return [1, 3, 5, 7, 9]. Make sure it also works with negative step values so that range(5, 2, -1) produces [5, 4, 3, 2].

```javascript 
// Your code here.

console.log(range(1, 10));
// → [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
console.log(range(5, 2, -1));
// → [5, 4, 3, 2]
console.log(sum(range(1, 10)));
// → 55
```

<details>
  <summary>Solution</summary>
  
```javascript 
function range(start, end, stepValue = 1) {
  let arr = []; 
  if (stepValue < 0 && start > end) {
    for (let index = start; index >= end; index -= Math.abs(stepValue)) {
      arr.push(index);
    }
  } else if (stepValue > 0 && start < end) {
    for (let index = start; index <= end; index += stepValue) {
      arr.push(index);
    }
  }
  return arr; 
}

function sum(numbers) {
  let result = 0; 
  for (const num of numbers) {
    result += num; 
  }
  return result; 
}

console.log(range(1, 10)); // [1, 2, 3, 4,  5, 6, 7, 8, 9, 10]
console.log(range(5, 2, -1)); // [ 5, 4, 3, 2 ]
console.log(sum(range(1, 10))); // 55
```

</details> 

***

## Resources 

1. [MDN - Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
