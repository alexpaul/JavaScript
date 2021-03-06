# Control Flow 

## Equality 

```javascript 
const dataTypeComparisons = '42' == 42; // data type conversion comparisons
console.log(dataTypeComparisons); // true

const equaliyComparison = '42' === 42; // we always want to use === when doing equaliy comparison
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

## Logical operators, `&&, ||`

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

## Challenges 

#### Challenge 1

Write a JavaScript conditional statement to find the sign of product of three numbers.
Display the specified sign.

_Sample numbers : 3, -7, 2_  
_Output : The sign is -_  

<details>
  <summary>Solution</summary>
 
```javascript
const num1 = 1, num2 = -8, num3 = 4; 
const product = num1 * num2 * num3; 
if (product < 0) {
  console.log('The sign is -')
} else {
  console.log('The sign is +')
}
```
 
</details>

***

#### Challenge 2 

Prompt the user for a number that is greater than 100 but less than 2000 and store this as a variable named user.

Write an if statement that checks to see if user is greater than 100 and less than 2000.

If it is then it should assign message1 to a variable named result. If it is not then it should assign message2 instead.

```javascript
const message1 = 'You are amazingly correct!';
const message2 = 'Awww, it looks like that number is not correct. Try again!';
```

<details>
  <summary>Solution</summary> 
  
```javascript 
const message1 = 'You are amazingly correct!';
const message2 = 'Awww, it looks like that number is not correct. Try again!';
 
const user = prompt('Please enter a number that is greater than 100 and less than 2000.'); 

const userNumber = parseInt(user);

let result = '';

if (userNumber > 100 && userNumber < 2000) {
  result = message1; 
} else {
  result = message2; 
}

console.log(result);
```
  
</details> 

***


#### Challenge 3

The Grade Assigner

Write a function named assignGrade that:
  * takes 1 argument, a number score.
  * returns a grade for the score, either "A", "B", "C", "D", or "F".

Call that function for a few different scores and log the result to make sure it works.

<details>
  <summary>Solution</summary> 
  
```javascript 
function assignGrade(score) {
  if (typeof score !== 'number') {
    console.log('Score is an invalid number.'); 
    return '';
  }
  if (score < 0) {
    console.log('Score should be non-negative.'); 
    return ''; 
  }
  switch (true) {
    case (score >= 90):
      return 'A'; 
    case (score >= 80 && score <= 89): 
      return 'B'; 
    case (score >= 70 && score <= 79): 
      return 'C'; 
    case (score >= 60 && score <= 69): 
      return 'D'; 
    default: 
      return 'F'; 
  }
}

console.log(assignGrade(90)); // A 
console.log(assignGrade(89)); // B 
console.log(assignGrade(79)); // C
console.log(assignGrade(69)); // D
console.log(assignGrade(59)); // F
```
  
</details> 

***

#### Challenge 4

The World Translator

Write a function named helloWorld that:
  * takes 1 argument, a language code (e.g. "es", "de", "en")
  * returns "Hello, World" for the given language, for atleast 3 languages. It should default to returning English.

Call that function for each of the supported languages and log the result to make sure it works.

<details> 
  <summary>Solution</summary> 
  
```javascript 
function helloWorld(languageCode) {
  if (typeof languageCode !== 'string') {
    console.log('Not a valid string code.'); 
    return;
  }
  const defaultTranslation = 'Hello World';
  languageCode = languageCode.toLowerCase(); 
  switch (languageCode) {
    case 'en':
      return defaultTranslation;
    case 'de': 
      return 'Hallo Welt'; 
    case 'se': 
      return 'Hej världen'; 
    case 'fr': 
      return 'Bonjour le monde'; 
    case 'es':
      return 'Hola Mundo.'; 
    default: 
      return defaultTranslation;
  }
}

console.log(helloWorld('fr')); // Bonjour le monde
console.log(helloWorld('se')); // Hej världen
console.log(helloWorld('ES')); // Hola Mundo 
console.log(helloWorld('alex')); // Hello World
```
  
</details> 

***

