# Functions 

## Basic Named Function

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
