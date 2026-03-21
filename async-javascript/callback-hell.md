# Callback Hell in JavaScript 

## What is Callback Hell?

Callback Hell happens when multiple callbacks are nested inside each other, making the code:
- Hard to read 
- Hard to debug 
- Hard to maintain 

## Why Does Callback Hell Happen?

JavaScript uses callbacks to handle asynchronous operations like:
- API calls
- File reading
- Timers

When we depend on one async task after another, we start nesting callbacks.

---

### Basic Callback Example

```js
setTimeout(() => {
  console.log("Step 1");

  setTimeout(() => {
    console.log("Step 2");

    setTimeout(() => {
      console.log("Step 3");

      setTimeout(() => {
        console.log("Step 4");
      }, 1000);

    }, 1000);

  }, 1000);

}, 1000);
```

### Problems in this code:

Deep nesting 

Difficult to understand flow

Error handling becomes messy

#### Problems with Callback Hell

  - Readability 	Hard to understand

  - Maintainability 	Hard to modify

  - Debugging 	Errors are difficult to trace

  - Error Handling 	Becomes complex

## How to Avoid Callback Hell

### 1. Use Promises

```js
loginUser(user)
  .then(getUserData)
  .then(getOrders)
  .then(processPayment)
  .then(() => console.log("Done"))
  .catch(err => console.log(err));
```

### 2. Use Async/Await (Best Approach)

```js
async function process() {
  try {
    const userData = await loginUser(user);
    const data = await getUserData(userData);
    const orders = await getOrders(data);
    await processPayment(orders);

    console.log("Done");
  } catch (err) {
    console.log(err);
  }
}
```

### 3. Use Named Functions

Instead of nesting:

setTimeout(step1, 1000);

function step1() {
  console.log("Step 1");
  setTimeout(step2, 1000);
}

function step2() {
  console.log("Step 2");
}


## Summary

Callback Hell means Nested callbacks

Makes code unreadable

Use Promises or Async/Await