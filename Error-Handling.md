# Error Handling 

## `throw`

```javascript 
throw 'someException'; 
```

## `try{}catch{}`

```javascript 
function fetchData() {
  throw 'fetchingError'; 
}

function logError(error) {
  console.log(error); 
}

try {
  fetchData(); 
} catch(error) {
  console.log('Error occured');
  logError(error); 
}
```

## `try{}catch{}finally{}`

```javascript 
try {
  throw someErrorThrownHere; 
} catch(error) {
  logError(error); 
} finally {
  console.log('This block of code will always execute'); 
}
```
