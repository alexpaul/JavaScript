# Error Handling 

> The throw statement throws a user-defined exception. Execution of the current function will stop (the statements after throw won't be executed), and control will be passed to the first catch block in the call stack. If no catch block exists among caller functions, the program will terminate.

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
  throw 'someErrorThrownHere'; 
} catch(error) {
  logError(error); 
} finally {
  console.log('This block of code will always execute'); 
}
```

## Resources 

1. [MDN - throw](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/throw)
1. [MDN - Error](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error)
