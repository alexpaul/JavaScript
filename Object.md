# Object 

Objects have properties and methods associated with them. 


An example of an array of objects.

```javascript
const technologyStacks = [
  { 
    role: 'iOS Developer', 
    userInterface: ['UIKit', 'SwiftUI'],
    codingPlatform: ['Xcode', 'AppCode'], 
    languages: ['Swift', 'Objective-C'], 
    backend: ['Firebase', 'Realm'] 
  },
  { 
    role: 'Full-Stack Web Developer',
    userInterface: ['React, CSS, HTML'], 
    codingPlatform: ['Visual Studio Code', 'WebStorm'], 
    languages: ['JavaScript', 'TypeScript'], 
    backend: ['Express', 'Node', 'PostgresSQL'] 
  }
]
```

## 1. Creating objects using object literal 

```javascript 
const fellow = { 
  // properties
  name: 'Brian',
  stack: 'iOS',
  isMentor: true,

  // methods 
  info: function() {
    console.log(`Hi my name is ${this.name}.`)
  }
};

console.log(fellow.stack); // iOS
fellow.info(); // Hi my name is Brian.
```

## 2. Creating objects using constructors 

```javascript 
const book = new Object(); 
book.title = '1984'; 
book.author = 'George Orwell'; 
book.isAvailable = false; 

book.checkIn = function() {
  this.isAvailable = true; 
};

book.checkOut = function() {
  this.isAvailable = false; 
};

console.log(typeof book); // object

book.checkIn(); 

book.isAvailable // true
```

## 3. Accessing object properties 

#### Dot Notation 

```javascript 
console.log(book.title);
```

#### Bracket Notation 

```javascript 
const value = book['title']; 
console.log(value); 
```

## 4. Accessing methods 

```javascript 
book.checkIn // [Function: checkIn]

// invoke (call) the checkIn function
book.checkIn(); 
book['checkin'];
```

## 5. The `this` keyword (context)

```javascript 
const language = {
  name: 'Swift', 
  platform: 'iOS',
  currentVersion: 5.2, 

  update: function() {
    this.currentVersion = 5.3; // refers to the property `currentVersion`
    return this; // refers to the object instance
  }
}

console.log(language.update()); // prints language object
/*
{
  name: 'Swift',
  platform: 'iOS',
  currentVersion: 5.3,
  update: [Function: update]
}
*/
```

#### Global `this`

The `this` global context in a Node environment and Browser environment varies. 

Example of running `this` in a `repl.it` environment provides the following output 

<details> 
  <summary>`this` global output</summary> 
  
```javascript 
{
  console: {
    log: [Function: log],
    warn: [Function: warn],
    dir: [Function: dir],
    time: [Function: time],
    timeEnd: [Function: timeEnd],
    timeLog: [Function: timeLog],
    trace: [Function: trace],
    assert: [Function: assert],
    clear: [Function: clear],
    count: [Function: count],
    countReset: [Function: countReset],
    group: [Function: group],
    groupEnd: [Function: groupEnd],
    table: [Function: table],
    debug: [Function: debug],
    info: [Function: info],
    dirxml: [Function: dirxml],
    error: [Function: error],
    groupCollapsed: [Function: groupCollapsed],
    Console: [Function: Console],
    profile: [Function: profile],
    profileEnd: [Function: profileEnd],
    timeStamp: [Function: timeStamp],
    context: [Function: context]
  },
  alert: [Function: log],
  prompt: [Function: prompt],
  confirm: [Function: confirm],
  module: Module {
    id: '.',
    path: '/home/runner/JavaScript-Playgrounds',
    exports: {},
    parent: null,
    filename: '/home/runner/JavaScript-Playgrounds/index.js',
    loaded: false,
    children: [],
    paths: [
      '/home/runner/JavaScript-Playgrounds/node_modules',
      '/home/runner/node_modules',
      '/home/node_modules',
      '/node_modules'
    ]
  },
  require: [Function: bound ],
  __dirname: '/home/runner/JavaScript-Playgrounds',
  __filename: '/home/runner/JavaScript-Playgrounds/index.js',
  global: {
    console: {
      log: [Function: log],
      warn: [Function: warn],
      dir: [Function: dir],
      time: [Function: time],
      timeEnd: [Function: timeEnd],
      timeLog: [Function: timeLog],
      trace: [Function: trace],
      assert: [Function: assert],
      clear: [Function: clear],
      count: [Function: count],
      countReset: [Function: countReset],
      group: [Function: group],
      groupEnd: [Function: groupEnd],
      table: [Function: table],
      debug: [Function: debug],
      info: [Function: info],
      dirxml: [Function: dirxml],
      error: [Function: error],
      groupCollapsed: [Function: groupCollapsed],
      Console: [Function: Console],
      profile: [Function: profile],
      profileEnd: [Function: profileEnd],
      timeStamp: [Function: timeStamp],
      context: [Function: context]
    },
    alert: [Function: log],
    prompt: [Function: prompt],
    confirm: [Function: confirm],
    module: Module {
      id: '.',
      path: '/home/runner/JavaScript-Playgrounds',
      exports: {},
      parent: null,
      filename: '/home/runner/JavaScript-Playgrounds/index.js',
      loaded: false,
      children: [],
      paths: [Array]
    },
    require: [Function: bound ],
    __dirname: '/home/runner/JavaScript-Playgrounds',
    __filename: '/home/runner/JavaScript-Playgrounds/index.js',
    global: [Circular],
    clearInterval: [Function: clearInterval],
    clearTimeout: [Function: clearTimeout],
    setInterval: [Function: setInterval],
    setTimeout: [Function: setTimeout] {
      [Symbol(nodejs.util.promisify.custom)]: [Function]
    },
    queueMicrotask: [Function: queueMicrotask],
    clearImmediate: [Function: clearImmediate],
    setImmediate: [Function: setImmediate] {
      [Symbol(nodejs.util.promisify.custom)]: [Function]
    },
    checkForGlobalThis: [Function: checkForGlobalThis]
  },
  clearInterval: [Function: clearInterval],
  clearTimeout: [Function: clearTimeout],
  setInterval: [Function: setInterval],
  setTimeout: [Function: setTimeout] {
    [Symbol(nodejs.util.promisify.custom)]: [Function]
  },
  queueMicrotask: [Function: queueMicrotask],
  clearImmediate: [Function: clearImmediate],
  setImmediate: [Function: setImmediate] {
    [Symbol(nodejs.util.promisify.custom)]: [Function]
  },
  checkForGlobalThis: [Function: checkForGlobalThis]
}
```

</details> 

#### Compare `this` context using `globalThis`

```javascript
function checkForGlobalThis() {
  return this; // `this` here is bound to the `global` scope
}

const person = {
  name: 'Kate', 
  
  info: function() {
    return this; // does refer to the global context but refers to the object instance
  }
}

console.log(checkForGlobalThis() === globalThis); // true

console.log(person.info() === globalThis); // false 
```

## 6. Accessing ALL the `key, value` pairs of an Object using `Object.entries()`

> MDN documentation: The Object.entries() method returns an array of a given object's own enumerable string-keyed property [key, value] pairs, in the same order as that provided by a for...in loop. (The only important difference is that a for...in loop enumerates properties in the prototype chain as well). 

> The order of the array returned by Object.entries() does not depend on how an object is defined. If there is a need for certain ordering, then the array should be sorted first, like Object.entries(obj).sort((a, b) => b[0].localeCompare(a[0]));.

[more on `Object.entries()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/entries)

```javascript 
const grades = {
  adam: 85, 
  rachel: 90, 
  bob: 100, 
  cindy: 75
}; 

for (const [name, grade] of Object.entries(grades)) {
  console.log(`${name} grade is ${grade}`); 
}

/*
adam grade is 85
rachel grade is 90
bob grade is 100
cindy grade is 75
*/
```

## 7. Pass-by-reference and Pass-by-value 

```javascript 
const nancy = {
  name: 'Nancy'
}

const heather = {
  name: 'Heather'
}

function update(fellow1, fellow2) {
  fellow1 = { name: 'Tony' }; // changing the object itself doesn't change the insstance, pass-by-value
  fellow2.name = "Alex"; // changing the properties changes the insstance properties, pass-by-reference 
}

update(nancy, heather);

console.log(nancy); // { name: 'Nancy' }
console.log(heather); // { name: 'Alex' }
```

## Traditional JavaScript objects vs ES6 classes 

## Prototype objects 

```javascript 
// Here we are using upppercase to denote that Person is a type
// as opposed to a function person() 
function Person(first, last, age, gender, interests) {
  // property and method definitions 
  this.name = {
    'first': first, 
    'last': last 
  }
  this.age = age; 
  this.gender = gender; 
}

const person1 = new Person('Bob', 'Smith', 32, 'male', ['music', 'skiing']);
```

## ES6 classes 

```javascript 
// ES6 classes 

class Person {
  constructor() {

  }

  greeting() {

  }

  farewell() {
    
  }
```


## 8. Challenges 

#### Challenge 1

The Recipe Card   

Never forget another recipe!   

* Create an object to hold information on your favorite recipe. It should have properties for title (a string), servings (a number), and ingredients (an array of strings).

* On separate lines (one console.log statement for each), log the recipe information so it looks like:
  * Mole
  * Serves: 2
  * Ingredients:
  * cinnamon
  * cumin
  * cocoa

<details> 
  <summary>Solution</summary> 
  
```javascript 
const recipe = {
  title: 'Strawberry Cake',
  servings: 8, 
  ingredients: ['Flour', 'Butter', 'Strawberries', 'Sugar']
}

for (const [key, value] of Object.entries(recipe)) {
  if (key === 'title') {
    console.log(value); 
  }
  if (key === 'servings') {
    console.log(`Servings: ${value}`);
  }
  if (key === 'ingredients') {
    console.log('Ingredients:')
    for (const ingredient of value) {
      console.log(ingredient); 
    }
  }
}

/*
Strawberry Cake
Servings: 8
Ingredients:
Flour
Butter
Strawberries
Sugar
*/
```
  
</details> 

***

#### Challenge 2

Write a JavaScript program to list the properties of a JavaScript object.

Sample object:

```javascript
const student = {
  name : "David Rayy",
  sclass : "VI",
  rollno : 12 
};

_Sample Output: [ 'name', 'sclass', 'rollno' ]_ 


const student = {
  name : "David Rayy",
  sclass : "VI",
  rollno : 12 
};

console.log(Object.keys(student));
```

<details> 
  <summary>Solution</summary> 
  
```swift 
const student = {
  name : "David Rayy",
  sclass : "VI",
  rollno : 12 
};

console.log(Object.keys(student)); // [ 'name', 'sclass', 'rollno' ]
```
  
</details> 

***

#### Challenge 3 

Create a class called `Person` which accepts the name of a person as a string, and his/her age as a number.

The Person class should have a method called describe which returns a string with the following syntax: "name, age years old". So for example, if John is 19 years old then the function describe of his object will return "John, 19 years old".

<details>
  <summary>Solution</summary>

```javascript
class Person {
  constructor(name, age) {
    this.name = name; 
    this.age = age;
  }

  describe() {
    return `${this.name}, ${this.age} years old.`
  }
}

const george = new Person('George', 29);
george.describe(); // George, 29 years old.
```

</details> 

***

#### Challenge 4 

The Reading List

Keep track of which books you read and which books you want to read!

* Create an array of objects, where each object describes a book and has properties for the title (a string), author (a string), and alreadyRead (a boolean indicating if you read it yet).
* Iterate through the array of books. For each book, log the book title and book author like so: "The Hobbit by J.R.R. Tolkien".
* Now use an if/else statement to change the output depending on whether you read it yet or not. If you read it, log a string like 'You already read "The Hobbit" by J.R.R. Tolkien', and if not, log a string like 'You still need to read "The Lord of the Rings" by J.R.R. Tolkien.'

<details>
  <summary>Solution</summary>
  
```javascript
const readingList = [
 { title: 'Good to Great', author: 'Jim Collins', alreadyRead: false }, 
 { title: 'Unbroken', author: 'Laura Hillenbrand', alreadyRead: true },
 { title: 'Next', author: 'Michael Crichton', alreadyRead: true }
]

for (const book of readingList) {
  const message = (book.alreadyRead) ? 'You already read' : 'You still need to read'; 
  console.log(`${message} \"${book.title}\" by ${book.author}.`); 
}

/*
You still need to read "Good to Great" by Jim Collins.
You already read "Unbroken" by Laura Hillenbrand.
You already read "Next" by Michael Crichton.
*/
```

</details> 

***

#### Challenge 5

Write a function called `cashRegister` that takes a shopping cart object. The object contains item names and prices (itemName: itemPrice). The function should return the total price of the shopping cart.

```javascript
Example
// Input
const cartForParty = {  
  banana: '1.25',
  handkerchief: '.99',
  tShirt: '25.01',
  apple: '0.60',
  nalgene: '10.34',
  proteinShake: '22.36'
};

// Output
cashRegister(cartForParty)); // 60.55
```

<details> 
  <summary>Solution</summary> 
  
```javascript 
function cashRegister(shoppingCart) {
  let totalPrice = 0; 
  for (let [itemName, price] of Object.entries(shoppingCart)) {
    price = parseFloat(price); 
    totalPrice += price;
  }
  return totalPrice; 
}

const cartForParty = {  
  banana: '1.25',
  handkerchief: '.99',
  tShirt: '25.01',
  apple: '0.60',
  nalgene: '10.34',
  proteinShake: '22.36'
};

let totalPrice = cashRegister(cartForParty);
console.log(`The total price of the shopping cart is ${totalPrice}`); 
// The total price of the shopping cart is 60.55
```
  
</details> 

***

#### Challenge 6

Write a class `Vec` that represents a vector in two-dimensional space.

It takes x and y parameters (numbers), which it should save to properties of the same name.

Give the Vec prototype two methods, `plus` and `minus`,
that take another vector as a parameter and return a new vector
that has the sum or difference of the two vectors’ (`this` and the parameter) x and y values.

Add a getter property `length` to the prototype that computes the length of the vector—that is,
the distance of the point (x, y) from the origin (0, 0).

```javascript
// Your code here.

console.log(new Vec(1, 2).plus(new Vec(2, 3)));
// → Vec{x: 3, y: 5}
console.log(new Vec(1, 2).minus(new Vec(2, 3)));
// → Vec{x: -1, y: -1}
console.log(new Vec(3, 4).length);
// → 5
```

<details> 
  <summary>Solution</summary> 
  
```javascript 
class Vec {
  constructor(x,y) {
    this.x = x; 
    this.y = y; 
  }

  get length() {
    return Math.sqrt((this.x * this.x) + (this.y * this.y)); 
  }

  plus(vec) {
    return new Vec(this.x + vec.x, this.y + vec.y)
  }

  minus(vec) {
    return new Vec(this.x - vec.x, this.y - vec.y)
  }
}

console.log(new Vec(1, 2).plus(new Vec(2, 3))); // Vec { x: 3, y: 5 }
console.log(new Vec(1, 2).minus(new Vec(2, 3))); // Vec { x: -1, y: -1 }
console.log(new Vec(3, 4).length); // 5
```
  
</details> 

***

#### Challenge 7

Define a `repeatify` function on the `String` object. The function accepts an integer that specifies how many times the string has to be repeated. The function returns the string repeated the number of times specified. For example:

```javascript
console.log('hello'.repeatify(3));
```

Should print `hellohellohello`.

<details>
  <summary>Solution</summary> 
  
```javascript 
String.prototype.repeatify = function(times) {
  let str = '';
  for (let index = 0; index < times; index++) {
    str += this;  
  }
  return str; 
}
'Alex is coding......'.repeatify(3);

/*
Alex is coding......Alex is coding......Alex is coding......
*/
```
  
</details> 

*** 


## 9. Resources 

1. [MDN - Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
1. [Stackoverflow - Is JavaScript a pass-by-reference or pass-by-value language?](https://stackoverflow.com/questions/518000/is-javascript-a-pass-by-reference-or-pass-by-value-language)
