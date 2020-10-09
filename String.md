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

## Converting String to Number 

```javascript 
let stringNum = '150'; 

console.log(parseInt(`${2020 + 1}`)); // 2021
console.log(parseInt(stringNum)); // 150
console.log(parseInt('eight')); // NaN
console.log(parseInt('0xF')); // hexadecimal number
```

## Converting String to Float

```javascript 
console.log(parseFloat(2.50 + 0.13)); // 2.63
console.log(parseFloat('five')); // NaN
```

## Converting Number to String

```javascript 
let number = 150; 
let floatValue = 1.50; 

console.log(number.toString()); // '150'
console.log(floatValue.toString()); // '1.50'
console.log((100).toString()); // '100'
```
