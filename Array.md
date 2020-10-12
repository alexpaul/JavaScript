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

## Resources 

1. [MDN - Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
