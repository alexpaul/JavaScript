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
