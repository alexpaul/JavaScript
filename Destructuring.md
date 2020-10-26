# Destructuing in JavaScript

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
2. Using destructing to get to only the values we need from an object. 
3. Prints out only the { data } key,value pair 
*/

/*
Use destructuring to retrieve status, add to step 2 above as we can use comma delimeter to include more properties for destructuring
*/
```
