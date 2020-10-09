## Math 


## Basic arithmetic 

* Addition 
* Subtraction 
* Mutiplication 
* Division 

#### Addition 

```javascript 
let number = 100; 
console.log(`${number + 10}`); // 110 
```

#### Subtraction 

```javascript 
let number = 100; 
console.log(`${number - 50}`); // 50 
```

#### Mutiplication 

```javascript 
let number = 100; 
console.log(`${number * number}`); // 10000 
```

#### Division 

```javascript 
let number = 100; 
console.log(`${number / 10}`); // 10 
```

## Increment `++`

```javascript 
let currentYear = 2020; 
let nextYear = ++currentYear; 
console.log(`Next year is ${nextYear}`); // Next year is 2021
```

## Decrement `--`

```javascript 
let countdown = 10; 
--countdown; 
console.log(`Current countdown is ${countdown}`); // Current countdown is 9
```

## Modulo / Remainder operator `%`

```javascript 
let number = 15; 
let remainder = number % 10; 
console.log(`The remainder is ${remainder}`) // 5
```

## Using the `Math` object

> MDN documentation: Math is a built-in object that has properties and methods for mathematical constants and functions. It’s not a function object.

> Note: Math works with the Number type. It doesn't work with BigInt.

#### `Pi`
```javascript 
const pi = Math.PI; 
console.log(`Pi is ${pi}`); // Pi is 3.141592653589793
```

#### `sqrt()`
```javascript 
const number = 81; 
console.log(`The sqrt of ${number} is ${Math.sqrt(number)}`); // The sqrt of 81 is 9
```
