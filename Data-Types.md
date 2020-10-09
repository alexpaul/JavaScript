# Data Types

JavaScript is a weakly typed language. 

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

#### `instanceof`

Returns a Boolean of if a value matches the data type. 

## Equality 

```javascript 
let x = 0 == ''; // true, type coerced (evaluates as the same type) 

let x = 0 === ''; // false, better usage for equality as it respects the types in the case of `===`
```

> Reminder: Always use the `===` to test types for equality. 
