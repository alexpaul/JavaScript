# JSON 

## Converting an Object to JSON data `JSON.stringify()`

```javascript 
const book = new Object({
  title: "1984", 
  author: "George Orwell"
})

console.log(typeof book); 
console.log(book); // object

const books = [
  new Object({ title: "1984", author: "George Orwell"}), 
  new Object({ title: "Becoming", author: "Michelle Obama"}), 
  new Object({ title: "Snow Crash", author: "Neal Stephenson"}), 
  new Object({ title: "Predictably Irrational", author: "Dan Ariely"}), 
]

console.log(typeof books); // object
console.log(books instanceof Array) // true
console.log(books); 

// JSON.stringify - JavaScript to JSON 
let bookJSON = JSON.stringify(book); 
console.log(typeof bookJSON); // string
console.log(bookJSON);
// {"title":"1984","author":"George Orwell"}

let booksJSON = JSON.stringify(books); 
console.log(typeof booksJSON); // string 
console.log(booksJSON);
/*
[{"title":"1984","author":"George Orwell"},
{"title":"Becoming","author":"Michelle Obama"},
{"title":"Snow Crash","author":"Neal Stephenson"},
{"title":"Predictably Irrational","author":"Dan Ariely"}]
*/
```

## Converting JSON to JavaScript `JSON.parse()`

```javascript 
let data = bookJSON;
let parsed = JSON.parse(data); 
console.log(parsed);
// { title: '1984', author: 'George Orwell' }
console.log(Array.isArray(parsed)); // false 
console.log("Num items " + parsed.length); 

let parsedBooks = JSON.parse(booksJSON);
console.log(parsedBooks); 
console.log(Array.isArray(parsedBooks)); // true
console.log(`There are ${parsedBooks.length} books in the collection.`)
// There are 4 books in the collection.
console.log(`The author of the second book is ${parsedBooks[1].author}`)
// The author of the second book is Michelle Obama
```
