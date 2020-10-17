# Promises 

## Asynchronous programming and Promises in JavaScript 

We use asynchronous programming to avoid blocking the main thread of a running application. 

Asynchronous programming is used to accomplish the following: 

* File I/O
* REST calls 
* Database operations 
* Complex computations

## Callbacks 

Before Promises JavaScript used callbacks. The challenge with callbacks is with multiple asynchronous work depending upon each other you will run into nested callbacks.

```javascript 
function callback() {
  console.log('Timeout completed.'); 
}

setTimeout(callback, 5_000); // wait 5 seconds
```


## Promises

> MDN documentation: The Promise object represents the eventual completion (or failure) of an asynchronous operation and its resulting value.

Promises works such that when an asynchronous block of code completes it will let the caller know and provide a result. 

```javascript 
function promiseTimeout(ms) {
  return new Promise((resolve, reject) => { // anonymous funciton
    setTimeout(resolve, ms);  // call the resolve function
  });
}
```

#### Using `.then` syntax to work with a `Promise` .

```javascript
promiseTimeout(2000)
  .then(() => {
    console.log('Done!');
  }).then(() => {
    console.log('Also done!'); 
    return Promise.resolve(42);
  }).then((result) => {
    console.log(result);
  }).catch(() => {
    console.log('Error!'); 
  }) 
```

#### Using `async/await` syntax to work with a `Promise` . 

> MDN documentation: An async function is a function declared with the async keyword. Async functions are instances of the AsyncFunction constructor, and the await keyword is permitted within them. The async and await keywords enable asynchronous, promise-based behavior to be written in a cleaner style, avoiding the need to explicitly configure promise chains.

```javascript 
async function longRunningOperation() { // can be from a network call
  return 42; // similar to resolve(42) when using .then syntax
}

async function run() {
  // await allows for thread to continue without being blocked 
  console.log('Start'); 
  await promiseTimeout(2000); // 2 seconds, "pauses" but main thread is not blocked
  // await required or you will get unusual behavior or lack of a valid result from the Promise

  const response = await longRunningOperation(); 
  console.log(response);

  console.log('Stop'); 
}

run();
```

## Resources 

1. [MDN - Using Promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises)
1. [MDN - Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
1. [MDN - async function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)
