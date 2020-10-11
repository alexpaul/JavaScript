# Variables 

## `var`

> available anwhere within the function scoped even before it is defined.

```javascript 
var language = 'Objective-C';
language = 'Swift';
```

```javascript 
language = 'Swift'; // can be used before it is defined
var language = 'Objective-C';
```

## `const`

> `const` represents a constant variable. This variable cannot be mutated. 

```javascript
const age = 10; 
age = 11; // typeError { Assignment to constant variable. }
```

## `let`

> `let` represents a mutable variable. It can be changed over time. 

```javascript
let year = 2020; 
year = 2021; 
```

> default to using `const` unless you need to mutate the variable, avoid using `var` as it has side effects as we saw from above in that it can be used before being initialized.

## Challenges 

#### Challenge 1 

Display the sum of 5 + 10, using two variables: x and y.

<details> 
  <summary>Solution</summary> 

```javascript 
let x = 5; 
let y = 10; 
console.log(`The sum of ${x} + ${y} is ${x + y}`); 
// The sum of 5 + 10 is 15
```

</details> 

#### Challenge 2

On one single line, declare three variables with the following names and values:

```javascript 
firstName = "John"
lastName = "Doe"
age = 35 
```

<details> 
  <summary>Solution</summary> 

```javascript 
let firstName = 'John', lastName = 'Doe', age = 35; 
```

</details> 

#### Challenge 3 

The Age Calculator

Want to find out how old you'll be? Calculate it!

Store your birth year in a variable.
Store a future year in a variable.
Calculate your 2 possible ages for that year based on the stored values.
For example, if you were born in 1988, then in 2026 you'll be either 37 or 38, depending on what month it is in 2026.
Output them to the screen like so: "I will be either NN or NN in YYYY", substituting the values.

<details> 
  <summary>Solution</summary> 

```javascript 
const birthYear = 1978; 
let currentYear = 1999; 

let age = currentYear - birthYear; 
let earlierMonth = age - 1; 

console.log(`I will be either ${earlierMonth} or ${age} in ${currentYear}`); 
// I will be either 20 or 21 in 1999 🥳 🍻
```
</details> 

#### Challenge 4 

The Fortune Teller

Why pay a fortune teller when you can just program your fortune yourself?

Store the following into variables: number of children, partner's name, geographic location, job title.
Output your fortune to the screen like so: "You will be a X in Y, and married to Z with N kids."


<details> 
  <summary>Solution</summary> 

```javascript 
let numberOfChildren = 11; 
let partnersName = 'Sarah'; 
let geographicLocation = {
  'latitude': 36.7783, 
  'longitude': 119.4179, 
  'state': 'California'
}
let jobTitle = 'Soccer Coach'

console.log(`You will be a ${jobTitle} in ${geographicLocation.state}, and married to ${partnersName} with ${numberOfChildren} kids`); 
// You will be a Soccer Coach in California and married to Sarah with 11 kids 🤯
```

</details>

## Challenge 5 

The Temperature Converter

It's hot out! Let's make a converter based on the steps here.

Store a celsius temperature into a variable.
Convert it to fahrenheit and output "NN°C is NN°F".
Now store a fahrenheit temperature into a variable.
Convert it to celsius and output "NN°F is NN°C."

<details> 
  <summary>Solution</summary> 

```javascript 
function celciusToFahrenheit(temp) {
  return (((temp / 5) * 9)  + 32).toFixed(2);
}

function fahrenheitToCelsius(temp) {
  return ((temp - 32) * 5 / 9).toFixed(2);
}

const celsius = 19; 
console.log(`${celsius}°C is ${celciusToFahrenheit(celsius)}°F`);
// 19°C is 66.20°F

const fahrenheit = 78;
console.log(`${fahrenheit}°F is ${fahrenheitToCelsius(fahrenheit)}°C`);
// 78°F is 25.56°C
```

</details>

