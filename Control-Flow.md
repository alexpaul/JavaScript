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

## Implicit false 

```javascript 
const name = ''; // (empty string) automatically converts to a false
if (name) {
  console.log('We have a name!'); 
} else {
  console.log('No name provided.')
}
```

## Case sensitive 

```javascript 
const statusMessage = 'error'; 

if (statusMessage === 'ERROR') { // false
  console.log('Something went wrong!')
} else {
  console.log('Looks great!')
}
```

## &&

```javascript 
const someStatus = 500; 

if (someStatus === 200) {
  console.log(); 
} else if (someStatus === 400 || someStatus === 500) {
  console.log('Error')
} else {
  console.log('Unknown error')
}
```

## Switch statement 

`break` is required as opposed to Swift or it will fallthrough. 

```javascript 
const status = 500; 
switch (status) {
  case 200: 
    console.log('Ok!'); 
    break; 
  case 400: 
  case 500: 
    console.log('Error'); 
    break; 
  default: 
    console.log('Unknown value');
    break; 
}
```

