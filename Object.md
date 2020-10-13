# Object 

Objects have properties and methods associated with them. 

## Creating objects using object literal 

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

## Creating objects using constructors 

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

## Accessing object properties 

#### Dot Notation 

```javascript 
console.log(book.title);
```

#### Bracket Notation 

```javascript 
const value = book['title']; 
console.log(value); 
```

## Accessing methods 

```javascript 
book.checkIn // [Function: checkIn]

// invoke (call) the checkIn function
book.checkIn(); 
book['checkin'];
```

## The `this` keyword (context)

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

```javascrpt 
function checkForGlobalThis() {
  return this; 
}

console.log(checkForGlobalThis() === globalThis); // true
```
