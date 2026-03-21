# Promises in JavaScript 

## What is a Promise?

A Promise is an object in JavaScript that represents the **future result** of an asynchronous operation.

## How to Create a New Promise?

You can create a Promise using the `Promise` constructor.

```javascript
const myPromise = new Promise((resolve, reject) => {
  let success = true;

  if (success) {
    resolve("Task completed successfully");
  } else {
    reject("Task failed");
  }
});
```

Explanation:

resolve() → called when task is successful

reject() → called when task fails

## States of a Promise

A Promise has 3 states:

### 1. Pending  - Initial state

    Task is still running

### 2. Fulfilled 

  Task completed successfully

resolve() is called

### 3. Rejected 

  Task failed

reject() is called

### Promise Flow

Pending → Fulfilled (resolve)
        → Rejected (reject)

## How to Consume a Promise?

You use .then() and .catch() to handle results.

Example:
```js
myPromise
  .then((result) => {
    console.log("Success:", result);
  })
  .catch((error) => {
    console.log("Error:", error);
  });
```

### Chaining Promises

You can chain multiple .then() calls:

```js
const promise = new Promise((resolve) => {
  resolve(10);
});

promise
  .then((num) => num * 2)
  .then((num) => num + 5)
  .then((result) => console.log(result));
```
 Output: 25

## Why Use Promises?

Promises solve problems of:

Callback Hell 

Inversion of Control issues

They make code: Cleaner, more readable and easier to manage

## Summary

Promise represents future result

Has 3 states: pending, fulfilled, rejected

Use .then() and .catch() to consume

Helps avoid callback hell

Async/Await makes it even simpler