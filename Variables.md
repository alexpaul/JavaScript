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
var firstName = 'John', lastName = 'Doe', age = 35; 
```

</details> 


