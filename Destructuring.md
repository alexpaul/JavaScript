# Destructuing in JavaScript

> MDN documentation: The destructuring assignment syntax is a JavaScript expression that makes it possible to unpack values from arrays, or properties from objects, into distinct variables.


## An example of object destructuring

```javascript 
// 1
const apiObject = {
  data: {
    user: 'Alex', 
    twitterHandle: 'alexpaul'
  }, 
  status: 200, 
}

// 2 
const { data } = apiObject; 

// 3
console.log(data); 
// { user: 'Alex', twitterHandle: 'alexpaul' }

/*
1. An object with various key, value pairs 
2. Using destructuring to get to only the properties we need from an object.
3. Prints out only the { data } key,value pair 
*/

/*
Exercise: use destructuring to retrieve status, add to step 2 above as we can use comma delimeter to include more properties for destructuring
*/
```

## Resources 

1. [MDN - Destructuring assignment](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)
