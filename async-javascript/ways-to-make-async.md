# Ways to Make JavaScript Code Asynchronous

JavaScript is **synchronous by default** (runs line by line).  
But in real-world apps, we need async behavior to:
- Call APIs
- Handle timers
- Read files
- Avoid blocking the UI

So we use different methods to make code **asynchronous (non-blocking)**.


## setTimeout()

Used to run code after a delay.   

### Example:
```js
console.log("Start");

setTimeout(() => {
  console.log("Hello after 2 seconds");
}, 2000);

console.log("End");
```
Output:
Start

End

Hello after 2 seconds

JS does not wait for setTimeout

## setInterval()

Runs code repeatedly after a fixed time.

Example:
```js
setInterval(() => {
  console.log("Running every 1 second");
}, 1000);
```
 Keeps running until stopped

 ## Callbacks

A callback is a function passed into another function.

Example:
```js
function fetchData(callback) {
  setTimeout(() => {
    callback("Data received");
  }, 2000);
}

fetchData((data) => {
  console.log(data);
});
```

 Problem: Can lead to callback hell

## Promises

Promises solve callback problems.

States:

Pending

Resolved

Rejected

Example:

```js
const promise = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve("Success");
  }, 2000);
});

promise
  .then((result) => {
    console.log(result);
  })
  .catch((error) => {
    console.log(error);
  });
```

 Cleaner than callbacks

## Async/Await

Best modern way to handle async code.

 Makes async code look like synchronous

Example:

```js
function fetchData() {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve("Data received");
    }, 2000);
  });
}

async function getData() {
  const data = await fetchData();
  console.log(data);
}

getData();
```

 Easy to read and write

## Summary

JS is synchronous by default

Async helps avoid blocking

Different ways:

setTimeout / setInterval

Callbacks

Promises

Async/Await

