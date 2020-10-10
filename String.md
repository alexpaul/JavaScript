# String 

## Doule quotes 

```javascript 
const doubleQuoteStr = "JavaScript"; 
```

## Single quotes 

```javascript 
let singleQuoteStr = 'JavaScript';
```

## Substitutions 

```javascript 
let count = 0 
console.log('Current count is %s', count); 
```

## Template literals 

Template literals are backtick embedded strings with the use of `${variableName}` as a placeholder.

#### Example 1

```javascript 
const value1 = 10;
const value2 = 23; 
console.log(`value 1 is ${value1} and value 2 is ${value2}, sum is ${value1 + value2}`);
// value 1 is 10 and value 2 is 23, sum is 33
```
##### Example 2 

```javascript 
let today = 'Friday'; 
let greeting = 'Thank God it\'s'; 

console.log(`${greeting} ${today}`);
```

## Concatenation 

```javascript 
const str1 = 'Learning';
const str2 = 'JavaScript';
console.log(str1 + ' ' +  str2); // Learning JavaScript
```

Be careful with accidentally thinking the logic below will result in a math addition

```javascript 
const value1 = '1';
const value2 = 1; 
// answer is 11 here as JavaScript will treat the evaluation as concatenation of two String not adding numbers e.g 1 + 1 is 2. 
console.log(value1 + value2) 
```

## Converting String to Number `parseInt()`

#### Example 1 

```javascript 
let stringNum = '150'; 

console.log(parseInt(`${2020 + 1}`)); // 2021
console.log(parseInt(stringNum)); // 150
console.log(parseInt('eight')); // NaN
console.log(parseInt('0xF')); // hexadecimal number
```

#### Example 2

```javascript 
console.log(parseInt('  123')); // 123, ignores the spaces 
console.log(parseInt('.123')); // NaN , sees a special character and return NaN (not a number)
console.log(parseInt('1 23')); // 1 , only parses the first number and ignores everything after the space
```

## Converting String to Float `parseFloat()`

```javascript 
console.log(parseFloat(2.50 + 0.13)); // 2.63
console.log(parseFloat('five')); // NaN
```

## Converting Number to String `toString()`

```javascript 
let number = 150; 
let floatValue = 1.50; 

console.log(number.toString()); // '150'
console.log(floatValue.toString()); // '1.50'
console.log((100).toString()); // '100'
```

## Challenges 

#### Challenge 1

Use escape characters to console log: We are "Vikings".

<details> 
  <summary>Solution</summary> 

```javascript 
console.log('We are \"Vikings\"'); // We are "Vikings"
```

</details>

#### Challenge 2

Create two constants to store "Hello" and "Swift" to form "Hello Swift". 

<details> 
  <summary>Solution</summary> 

```javascript 
const msg1 = 'Hello'; 
const msg2 = 'Swift'; 
console.log(msg1 + ' ' + msg2); // "Hello Swift"
```

</details>
