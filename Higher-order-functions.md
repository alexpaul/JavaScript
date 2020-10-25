# Higher order functions 

A higher-order function is a function that takes in another function or returns a function. Such functions include `map` and `filter`. 

## Re-creating the built-in `map` function

Custom map

```javascript 
function customMap(values, transform) {
  let tranformedArr = []; 
  for (const value of values) {
    const result = transform(value);
    tranformedArr.push(result); 
  }
  return tranformedArr; 
}
```

Usage

```javascript 
const numbers = [1, 2, 3, 4, 5, 6]; 
const squares = customMap(numbers, num => num * num )
console.log(squares); // [ 1, 4, 9, 16, 25, 36 ]
```
