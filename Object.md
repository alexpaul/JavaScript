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
