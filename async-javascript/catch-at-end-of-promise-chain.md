# Why `.catch()` Should Be Placed at the End of a Promise Chain ?

## What is `.catch()`?

`.catch()` is used to handle errors in a Promise chain.

It catches:
- Errors thrown in `.then()`
- Rejected promises


## Why Should `.catch()` Be at the End?

 Because `.catch()` handles errors from all previous steps.

If placed at the end:
- It can catch errors from every `.then()`

## Correct Way (Best Practice)

```javascript
Promise.resolve(10)
  .then((num) => {
    console.log("Step 1:", num);
    return num * 2;
  })
  .then((num) => {
    throw new Error("Error in Step 2");
  })
  .then((num) => {
    console.log("Step 3:", num); //  Skipped
  })
  .catch((err) => {
    console.log("Caught:", err.message);
  });
  ```

Output:

Step 1: 10

Caught: Error in Step 2

 .catch() at the end catches errors from ALL .then() above

## What Happens if .catch() is in the Middle?

```js
Promise.resolve(10)
  .then((num) => {
    throw new Error("Error in Step 1");
  })
  .catch((err) => {
    console.log("Caught:", err.message);
  })
  .then((num) => {
    console.log("Step 2:", num); //  This WILL run
  });
```
Output:

Caught: Error in Step 1

Step 2: undefined

Explanation:

.catch() handles the error

Then chain CONTINUES

Next .then() runs with undefined

## Problem with Middle .catch()

 It only handles errors before it
 
 Errors after it are NOT caught

```js
Promise.resolve(10)
  .then((num) => {
    return num * 2;
  })
  .catch((err) => {
    console.log("Caught:", err);
  })
  .then(() => {
    throw new Error("New Error!");
  });
```

This error is NOT caught!

Think of a production line:

If something fails anywhere:

Error handler at the END catches everything

## Summary

.catch() should be at the END of the chain

It catches errors from all previous .then()

Middle .catch() can break error flow

Always use one final .catch() for safety

Use .finally() after .catch() for cleanup