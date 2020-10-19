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


#### Using `+`

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

#### Using `concat()`

```javascript 
const firstName = 'John'; 
const lastName = 'Appleseed'; 
const formattedLastName = ` ${lastName}`
console.log(`The person\'s full name is ${firstName.concat(formattedLastName)}`); // The person's full name is John Appleseed
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

## 14. `indexOf()` 

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

## 16. `substring()`

Creates a `substring` from given indices.

```javascript 
const language = 'JavaScript';
const substring = language.substring(0, 4); 
console.log(substring); // Java 
```

## 17. `replace()`

Replace the occurrence of a substring with another string. 

```javascript 
let currentLanguage = 'I am currently learning Swift.'; 
currentLanguage = currentLanguage.replace('Swift', 'JavaScript');
console.log(currentLanguage); // I am currently learning JavaScript.
```

## 18. `slice()`

> MDN documentation: The slice() method extracts a section of a string and returns it as a new string, without modifying the original string.

```javascript
const str = 'JavaScript'; 

slicedStr = str.slice(0, 4); 
console.log(slicedStr); // Java

let slicedStr = str.slice(-6); 
console.log(slicedStr); // Script
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

#### Challenge 3 

Create a function called `verbing`. It should take a single argument, a string.
If its length is at least 3, it should add 'ing' to its end, unless it already ends in 'ing', in which case it should add 'ly' instead. 
If the string length is less than 3, it should leave it unchanged. For example:

```javascript
verbing('swim'): 'swimming'
verbing('swimming'): 'swimmingly'
verbing('go'): 'go'
```

<details> 
  <summary>Solution</summary> 

```javascript 
function verbing(inputString) {
  if (typeof inputString !== 'string') {
    console.log('Not a valid string.');
    return; 
  }
  if (inputString.length >= 3) {
    const lastCharIndex = inputString.length;
    const suffix = inputString.substring(lastCharIndex - 3, lastCharIndex);
    if (suffix === 'ing') {
      inputString += 'ly'
    } else {
      inputString += 'ing'; 
    }
  }
  return inputString; 
}

console.log(verbing('swim')); // swiming
console.log(verbing('swimming')); // swimmingly
console.log(verbing('go')); // go
```

</details>

***

#### Challenge 4 

Create a function called `mixUp`. It should take in two strings, and return the concatenation of the two strings (separated by a space) slicing out and swapping the first 2 characters of each. You can assume that the strings are at least 2 characters long. For example:

```javascript
mixUp('mix', pod'): 'pox mid'
mixUp('dog', 'dinner'): 'dig donner'
```

Look up the JavaScript string reference to find methods which may be useful!

<details>
  <summary>Solution</summary> 
  
```javascript 
function mixUp(str1, str2) {
  const str1Prefix = str1.substring(0, 2);
  const str2Prefix = str2.substring(0, 2); 

  str1 = str1.replace(str1Prefix, str2Prefix);
  str2 = str2.replace(str2Prefix, str1Prefix);  

  return str1.concat(` ${str2}`); 
}

console.log(mixUp('mix', 'pod')); // pox mid
console.log(mixUp('dog', 'dinner')); // dig donner
```
  
</details> 

*** 

#### Challenge 5

You can get the Nth character, or letter, from a string by writing "string"[N]. The returned value will be a string containing only one character (for example, "b"). The first character has position 0, which causes the last one to be found at position string.length - 1. In other words, a two-character string has length 2, and its characters have positions 0 and 1.

Write a function `countBs` that takes a string as its only argument and returns a number that indicates how many uppercase “B” characters there are in the string.

Next, write a function called `countChar` that behaves like countBs, except it takes a second argument that indicates the character that is to be counted (rather than counting only uppercase “B” characters). Rewrite countBs to make use of this new function.

```javascript
console.log(countBs("BBC")); // 2
console.log(countChar("kakkerlak", "k")); // 4
```

<details>
  <summary>Solution</summary> 
  
```javascript 
function countBs(inputString) {
  let charCounter = 0; 
  for (const char of inputString) {
    if (char === 'B') {
      charCounter += 1; 
    }
  }
  return charCounter; 
}
console.log(countBs("BBC")); // 2

function countChar(inputString, targetChar) {
  let count = 0; 
  for (const char of inputString) {
    if (char === targetChar) {
      count += 1; 
    }
  }
  return count; 
}
console.log(countChar("kakkerlak", "k")); // 4
```
  
</details> 

*** 

## Resources 

1. [MDN - String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
1. [StackOverflow - What is the difference between String.slice and String.substring?](https://stackoverflow.com/questions/2243824/what-is-the-difference-between-string-slice-and-string-substring)


