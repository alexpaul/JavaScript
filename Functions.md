# Functions 

## 1. Named Function

#### Function definition 

```javascript 
function printHello() {
  console.log('function says hello');
}

console.log(typeof printHello); // function
```

#### Function invocation - calling a function 

```javascript 
printHello(); // function says hello
```

#### Naming conventions  

Functions names are allowed to be made of $, _, a-z, A-z and 0-9. 

```javascript 
function $print() {}
function _print() {}
function p8rint() {}
```

#### Function parameters  

```javascript 
function greeting(name) { // name here is the parameter
  console.log(`Hello, ${name}`); 
}

// 'Alex' here is the argument passed into the function call
greeting('Alex'); // "Hello, Alex" 
```

#### Function return 

```javascript 
function addNumbers(a, b) {
  return a + b; 
}

const result = addNumbers(10, 5); 
console.log(result); // 15
```

## 2. Arrow Function or Fat Arrow Function 

> Please Note: `this` context in arrow functions inherits from it's parent's scope.

#### Single line and implicit return 

```javascript 
const add = (a, b) => a + b; 
console.log(add(4, 5)); // 9  
```


#### Multiple line and explicit return 

```javascript 
const subtract = (a, b) => {
  const result = a - b; 
  return result; 
}
console.log(subtract(1, 1)); // 0 
```

#### Swift closures as shown below is similar to arrow functions in JavaScript 

```swift 
let add: (Int, Int) -> Int = { $0 + $1 } // shorthand argument names and implicit return

print(add(4, 5)) // 9
```

## Challenges 

#### Challenge 1 

You know how old your dog is in human years, but what about dog years? Calculate it!

Write a function named calculateDogAge that:

takes 1 argument: your puppy's age.
calculates your dog's age based on the conversion rate of 1 human year to 7 dog years.
outputs the result to the screen like so: "Your doggie is NN years old in dog years!"
Call the function three times with different sets of values.
Bonus: Add an additional argument to the function that takes the conversion rate of human to dog years.

<details> 
  <summary>Solution</summary> 
  
```javascript 
function calculateDogAge(puppysAge, conversionRate) {
  if ((puppysAge < 1) || (conversionRate < 1)) {
    console.log('Invalid arguments.'); 
    return; 
  }
  const age = puppysAge * conversionRate; 
  console.log(`Your doggie is ${age} years old in dog years!`);
}

calculateDogAge(1, 7);  // Your doggie is 7 years old in dog years!
```
  
</details> 

#### Challenge 2

Write a JavaScript function that reverse a number.

_Example x = 32243_  
_Expected Output : 34223_   

<details> 
  <summary>Solution</summary> 
  
```javascript 
function reverseNumber(number) {
  const str = number.toString();
  let strReverse = '';
  for (const char of str) {
    strReverse = char + strReverse; 
  } 
  return parseInt(strReverse);
}

console.log(reverseNumber(32243)); // 34223
```
  
</details> 

#### Challenge 3 

Write a function to find the largest value in an array 

_Input: [-3, 5, 1, 89, 3, 0, -78, 1]_  
_Output: 89_  

<details> 
  <summary>Solution</summary> 
  
```javascript 
function largestValue(inputArray) {
  if (inputArray.length === 0) {
    return -1;
  }
  let currentLargest = inputArray[0]
  for (const element of inputArray) {
    if (element > currentLargest) {
      currentLargest = element;
    }
  }
  return currentLargest; 
}

console.log(largestValue([-3, 5, 1, 89, 3, 0, -78, 1])); // 89
console.log(largestValue([])); // -1 
```
  
</details> 

## Resources 

1. [MDN - Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)
