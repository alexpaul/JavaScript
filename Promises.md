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
