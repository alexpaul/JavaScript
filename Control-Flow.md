# Control Flow 

## Equality 

```javascript 
const dataTypeComparisons = '42' == 42; // data type conversion comparisons
console.log(dataTypeComparisons); // true

const equaliyComparison = '42' === 42; 
console.log(equaliyComparison); // false
```

## Not equal 

```javascript 
const strComparions = 'Alex' !== 'alex'
console.log(`string comparisons: ${strComparions}`); // true
```

## If statement 

```javascript 
const status = 200; 
if (status === 200) {
  console.log('OK!'); // OK! 
} else if (status === 400) {
  console.log('Error!'); 
} else {
  console.log('Unknown status'); 
}
```

## Ternary operator 


```javascript 
const message = (status === 200) ? 'Ok!' : 'Error!'; 
console.log(`using ternary operator: ${message}`); // using ternary operator: Ok!
```
