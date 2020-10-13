# JSON 

> MDN documentation: JSON is a syntax for serializing objects, arrays, numbers, strings, booleans, and null. It is based upon JavaScript syntax but is distinct from it: some JavaScript is not JSON.

## Object 

```json
{
  "firstName": "Alex", 
  "lastName": "Paul"
}
```

## Array 

```json 
[
	{
		"firstName": "Alex",
		"lastName": "Paul"
	},

	{
		"firstName": "John",
		"lastName": "Appleseed"
	}
]
```

## Converting an Object to JSON data `JSON.stringify()`

> MDN documentation: The `JSON.stringify()` method converts a JavaScript object or value to a JSON string, optionally replacing values if a replacer function is specified or optionally including only the specified properties if a replacer array is specified.

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

> MDN documentation: The `JSON.parse()` method parses a JSON string, constructing the JavaScript value or object described by the string. An optional reviver function can be provided to perform a transformation on the resulting object before it is returned.

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

## Resources 

1. [MDN - JSON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON) 
