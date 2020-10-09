# Data Types

JavaScript is a weakly (loosely) typed language as opposed to Swift that is a strongly typed language. 

#### Example of a weakly typed language

In this example the type `name` is not strongly tied to forever be a `String`. Re-assigning the data type to be a `Number` does not cause a compile-time error like a language like Swift. This causes the developer to check types when working through various coding logic. 

```javascript 
let name = "Alex"; 
name = 10; 

console.log(`${name + 7}`); // name here is a number
```

#### Example of a strongly typed language

In this Swift example we would get a compile time error as we cannot re-assign the name data type to an `Int`. 

```swift 
var name = "Alex";
name = 10; // COMPILER ERROR - cannot assign type Int to expected type String

print("\(name + 7)") // COMPILER ERROR - cannot convert value Int to expected value String
```


## Simple Types 

* Number (float) 
* String 
* Boolean
* Date
* Function 
* Array 
* Object 

## Special Types 

* NaN
* null 
* undefined

## Checking Type 

#### `typeof` 

Returns a string of the data type primitive. 

```javascript 
typeof('hello'); // string 
typeof(2); // number 
typeof(true); // boolean
```

#### `instanceof`

Returns a Boolean of if a value matches the data type. 

```javascript 
let str = new String() // new instance of String

if (str instanceof String) {
  console.log('It is a String value') // It is a String value
} 
```

#### More examples of testing `typeof` and `instanceof`

```javascript 
const fellows = ['Brian', 'Herb', 'Ashley', 'Kim']; 
const isFriday = true; 
const year = 2020;
const description = 'Incredible'; 
const person = {
  'firstName': 'Alex',
  'lastName': 'Paul'
};

function greeting(aPerson) {
  console.log(`The person\'s first name is ${aPerson.firstName}`);
}

console.log('----typeof----');
console.log(typeof fellows); // object
console.log(typeof isFriday); // boolean
console.log(typeof year); // number
console.log(typeof description); // string
console.log(typeof person); // object
console.log(typeof greeting); // function

console.log('----instanceof----');
console.log(fellows instanceof Array); // true 
console.log(isFriday instanceof Boolean); // false 
console.log(year instanceof Number); // false 
console.log(description instanceof String); // false 
console.log(person instanceof Object); // true
console.log(greeting instanceof Function); // true
```

> Note: console.log(isFriday instanceof Boolean) returns false since this is a literal declaration and NOT a constructor instance.

A constructor instance would be 

```javascript 
let newStringInstance = new String('Hello'); 

console.log(newStringInstance instanceof String); // true 
```


## Equality 

```javascript 
let x = 0 == ''; // true, type coerced (evaluates as the same type) 

let x = 0 === ''; // false, better usage for equality as it respects the types in the case of `===`
```

> Reminder: Always use the `===` to test types for equality. 
