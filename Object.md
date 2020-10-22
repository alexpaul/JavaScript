# Object 

Objects have properties and methods associated with them. 

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
Welcome to JavaSwift!
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

#### Challenge 3

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

#### Challenge 4

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


## 9. Resources 

1. [MDN - Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
1. [Stackoverflow - Is JavaScript a pass-by-reference or pass-by-value language?](https://stackoverflow.com/questions/518000/is-javascript-a-pass-by-reference-or-pass-by-value-language)
