# Promise Chaining in JavaScript 
## What is Promise Chaining?

Promise chaining means connecting multiple `.then()` methods to run asynchronous tasks step-by-step.

## How to Chain Promises using `.then()`

### Example:

```javascript
const promise = new Promise((resolve) => {
  resolve(10);
});

promise
  .then((num) => {
    console.log("Step 1:", num);
    return num * 2;
  })
  .then((num) => {
    console.log("Step 2:", num);
    return num + 5;
  })
  .then((result) => {
    console.log("Final Result:", result);
  });
  ```

Output:

Step 1: 10

Step 2: 20

Final Result: 25

 Each .then():

   - Receives value from previous step

   - Returns a new value for next step

   - Returning a Promise in Chain

You can also return a Promise inside .then().

```js
function asyncTask(num) {
  return new Promise((resolve) => {
    setTimeout(() => resolve(num * 2), 1000);
  });
}

asyncTask(5)
  .then((res) => {
    console.log("Step 1:", res);
    return asyncTask(res);
  })
  .then((res) => {
    console.log("Step 2:", res);
  });
```
## How to Handle Errors using .catch()

.catch() is used to handle errors in the entire promise chain.

Example:
```js
const promise = new Promise((resolve, reject) => {
  reject("Something went wrong");
});

promise
  .then((res) => {
    console.log(res);
  })
  .catch((err) => {
    console.log("Error:", err);
  });
```
### Error in Middle of Chain

If any .then() fails, control goes directly to .catch().

```js
Promise.resolve(10)
  .then((num) => {
    console.log(num);
    throw new Error("Error occurred!");
  })
  .then((num) => {
    console.log(num); // This will NOT run
  })
  .catch((err) => {
    console.log("Caught:", err.message);
  });
```
Output:  10

Caught: Error occurred!

 **Important:**    Once error occurs, remaining .then() are skipped

finally() in Promise Chain

finally() runs no matter what happens:

Success 

Failure 

Example:
```js
Promise.resolve("Success")
  .then((res) => {
    console.log(res);
  })
  .catch((err) => {
    console.log(err);
  })
  .finally(() => {
    console.log("Always runs");
  });
```

Example with Error:

```js
Promise.reject("Failed")
  .then((res) => {
    console.log(res);
  })
  .catch((err) => {
    console.log(err);
  })
  .finally(() => {
    console.log("Cleanup work");
  });
```

output :   Failed   Cleanup work

Flow:

Steps happen one after another

If error occurs → goes to .catch()

finally() always runs


## Summary

.then() is used for chaining

Each step passes value to next step

.catch() handles all errors in chain

finally() always executes

Keeps async code clean and readable