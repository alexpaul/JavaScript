# String 

## 1. Creating a String 

#### 1. Double quotes

```javascript 
const doubleQuoteStr = "JavaScript"; 
```

#### 2. Single quotes 

```javascript 
const singleQuoteStr = 'JavaScript';
```

#### 3. Template literals 

#### Substitutions 

```javascript 
let count = 0 
console.log('Current count is %s', count); 
```

#### Template literals

Template literals as opposed to substitions above are a better approach to using placeholders in a string.

Template literals are backtick embedded strings with the use of `${variableName}` as a placeholder.

```javascript 
const value1 = 10;
const value2 = 23; 
console.log(`value 1 is ${value1} and value 2 is ${value2}, sum is ${value1 + value2}`);
// value 1 is 10 and value 2 is 23, sum is 33
```

```javascript 
let today = 'Friday'; 
let greeting = 'Thank God it\'s'; 

console.log(`${greeting} ${today}`);
```

#### 4. String Object 

```javascript 
const stringObjectInstance = new String('String Object instance.'); 
console.log(stringObjectInstance); // [String: 'String Object instance.']
```

## 2. `length` of a String 

```javascript 
const language = 'JavaScript';
console.log(`The length of ${language} is ${language.length}`); // The length of JavaScript is 10
```

## 3. Accessing characters in a String

#### 1. Indexing a String 

```javascript 
const name = 'Alex';
const firstChar = name[0]; 
console.log(firstChar); // A
```

#### 2. Using `charAt()`

```javascript 
const name = 'Sarah';
const char = name.charAt(name.length - 1); 
console.log(char); // h
```

## 4. Comparing strings 

```javascript 
if ('a' < 'b') {
  console.log('a is less than b'); // a is less than b
}

if ('z' > 'Z') {
  console.log('Z is greater than z'); // Z is greater than z
}
```

## 5. `valueOf()` to access the value of an Object 

```javascript 
const stringObject = new String('Bob Marley'); 
console.log(stringObject); // [String: 'Bob Marley']
console.log(stringObject.valueOf()); // Bob Marley
```

## 6. `eval()`

```javascript 
console.log('10 + 5') // 10 + 5
console.log(eval('10 + 2')) // 12
```

## 7. Concatenation 

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

## 8. Escape characters 

Some escape characters `\', \" and \n` . See documentation for a list of more escape characters.

```javascript 
// \'
const escapeSingleQuote = 'Alex\'s Book'; 
console.log(escapeSingleQuote); // Alex's Book

// \"
const escapeDoubleQuote = 'Swift\"s latest version is 5.3';
console.log(escapeDoubleQuote); // Swift"s latest version is 5.3

// \n
const newLine = 'Today is Sunday.\nReturned from a weekend trip.';
console.log(newLine);
/*
Today is Sunday.
Returned from a weekend trip.
*/
```

## 9. Long literal strings 

```javascript 
const longLiteralString = "Welcome to JavaScript " + 
                          "the language " +
                          "of the web."
console.log(longLiteralString); 
```

## 10. Converting String to Number `parseInt()`

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

## 11. Converting String to Float `parseFloat()`

```javascript 
console.log(parseFloat(2.50 + 0.13)); // 2.63
console.log(parseFloat('five')); // NaN
```

## 12. Converting Number to String `toString()`

```javascript 
let number = 150; 
let floatValue = 1.50; 

console.log(number.toString()); // '150'
console.log(floatValue.toString()); // '1.50'
console.log((100).toString()); // '100'
```

## 13. `split()`

`split` is used to separate a given string by a given character and form and array. 

```javascript 
const str = 'Every developer should learn JavaScript.'; 

const spaceSeparated = str.split(' ');
console.log(spaceSeparated); // [ 'Every', 'developer', 'should', 'learn', 'JavaScript.' ]

const noCharSeparation = str.split(''); 
console.log(noCharSeparation);
/*
[
  'E', 'v', 'e', 'r', 'y', ' ', 'd',
  'e', 'v', 'e', 'l', 'o', 'p', 'e',
  'r', ' ', 's', 'h', 'o', 'u', 'l',
  'd', ' ', 'l', 'e', 'a', 'r', 'n',
  ' ', 'J', 'a', 'v', 'a', 'S', 'c',
  'r', 'i', 'p', 't', '.'
]
*/
```

## 14. `indexOf` 

`indexOf` is used to search the first occurrence of a substring. 

```javascript 
const str = 'Prior to Swift, iOS developers used Objective-C to write apps.'; 
const searchWord = 'Objective-C';
const index = str.indexOf(searchWord); 
console.log(`${searchWord} was found at index ${index}`); // Objective-C was found at index 36
```

## 15. `includes()`

`includes()` returns a boolean value indicating the presence of a substring in a given string. 

```javascript 
const str = 'Thanksgiving is one of the biggest holidays of the year';
const searchWord = 'Thanksgiving'; 
console.log(`\`${searchWord}\` ${str.includes(searchWord) ? `is` : `is not`} in the sentence.`);
// `Thanksgiving` is in the sentence. 
```

## 16. Challenges 

#### Challenge 1

Use escape characters to console log: We are "Vikings".

<details> 
  <summary>Solution</summary> 

```javascript 
console.log('We are \"Vikings\"'); // We are "Vikings"
```

</details>

***

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

***
