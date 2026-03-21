# Error Handling in Promise Chains 

## What happens when an error is thrown inside `.then()`?

When an error is thrown inside a `.then()` block:

 JavaScript immediately stops executing the remaining `.then()` blocks  
 Control is passed to the nearest `.catch()`  


## Basic Example

```javascript
Promise.resolve(10)
  .then((num) => {
    console.log("Step 1:", num);
    throw new Error("Something went wrong!");
  })
  .then((num) => {
    console.log("Step 2:", num); //  This will NOT run
  })
  .catch((err) => {
    console.log("Caught Error:", err.message);
  });
```

Output:

Step 1: 10

Caught Error: Something went wrong!

Explanation:

   - Error is thrown in first .then()
   
   - Next .then() is skipped
   
   - .catch() handles the error
 
   -  Error behaves like reject()

Throwing an error is same as returning a rejected promise.

```js
Promise.resolve()
  .then(() => {
    throw "Error occurred";
  })
  .catch((err) => {
    console.log(err);
  });
```

Equivalent to:

```js
Promise.reject("Error occurred")
  .catch((err) => console.log(err));
```
Error in Any .then() Goes to .catch()

```js
Promise.resolve(5)
  .then((num) => {
    return num * 2;
  })
  .then((num) => {
    throw new Error("Failed at Step 2");
  })
  .then((num) => {
    console.log(num); // ❌ Skipped
  })
  .catch((err) => {
    console.log("Caught:", err.message);
  });
```

- If there is NO .catch():

  Error becomes Unhandled Promise Rejection

```js
Promise.resolve()
  .then(() => {
    throw new Error("Boom!");
  });
```

This may:

Show error in console

Crash app (in some environments)

## Can we continue after .catch()?

- Yes 

After .catch(), the chain continues.

```js
Promise.resolve(10)
  .then((num) => {
    throw new Error("Oops!");
  })
  .catch((err) => {
    console.log("Handled:", err.message);
    return 100;
  })
  .then((num) => {
    console.log("Continued with:", num);
  });
```
Output:

Handled: Oops!

Continued with: 100

- If error happens in any step:

- Process stops

- Goes directly to error handler

## Summary

Throwing error inside .then() = rejected promise

.catch() handles errors from entire chain

Remaining .then() blocks are skipped after error

You can continue chain after .catch()

Always use .catch() to avoid crashes