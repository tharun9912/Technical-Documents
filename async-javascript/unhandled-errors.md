# Unhandled Errors in Promise Chains 

## What happens when an error is thrown inside `.then()` without `.catch()`?

When an error is thrown inside a `.then()` block and there is NO `.catch()`:

 The Promise becomes **rejected**  
 The error is **not handled**  
 JavaScript shows an **Unhandled Promise Rejection** warning/error  



## Basic Example

```javascript
Promise.resolve(10)
  .then((num) => {
    console.log("Step 1:", num);
    throw new Error("Something went wrong!");
  })
  .then((num) => {
    console.log("Step 2:", num); //  This will NOT run
  });
```
Output (Console):

Step 1: 10

Uncaught (in promise) Error: Something went wrong!

Explanation:

  - Error is thrown inside .then()

  - Next .then() is skipped

  - No .catch() → error is unhandled

## What is "Unhandled Promise Rejection"?

It means:
 A Promise failed (rejected)
 But no .catch() handled the error

Another Example

```js
Promise.resolve()
  .then(() => {
    throw "Error occurred!";
  });
```
Output:

Uncaught (in promise) Error occurred!

## Why is this Dangerous?

Problems:

 App may crash (especially in Node.js)

 Debugging becomes hard

 Unexpected behavior

 Poor user experience

## How JavaScript Handles It

In Browser:

  - Shows error in console

  - Does NOT stop entire app immediately

In Node.js:

   - May terminate the process (in strict modes)

   - Shows warning or error
 
   - You can catch it by adding .catch() at the end:

```js
Promise.resolve(10)
  .then((num) => {
    throw new Error("Oops!");
  })
  .catch((err) => {
    console.log("Caught:", err.message);
  });
```
Best Practice

 Always add .catch() to your Promise chains


## Summary

Throwing error inside .then() = rejected Promise

Without .catch() → Unhandled Promise Rejection

Remaining .then() blocks are skipped

Always handle errors using .catch()

Important for writing safe and stable code