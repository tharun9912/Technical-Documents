# Consuming Multiple Promises using Promise.all() 

## What is `Promise.all()`?

`Promise.all()` is a method in JavaScript used to run multiple promises **at the same time (in parallel)**.

In simple words:
- Start all tasks together
- Wait until ALL are finished
- Get all results at once


## Syntax

```javascript

Promise.all([promise1, promise2, promise3])
  .then((results) => {
    // results is an array
  })
  .catch((error) => {
    // handles error
  });
```

Simple Example
```js
function task1() {
  return new Promise((resolve) => {
    setTimeout(() => resolve("Task 1 done"), 1000);
  });
}

function task2() {
  return new Promise((resolve) => {
    setTimeout(() => resolve("Task 2 done"), 1000);
  });
}

function task3() {
  return new Promise((resolve) => {
    setTimeout(() => resolve("Task 3 done"), 1000);
  });
}

Promise.all([task1(), task2(), task3()])
  .then((results) => {
    console.log(results);
  })
  .catch((err) => {
    console.log(err);
  });
```

Output

["Task 1 done", "Task 2 done", "Task 3 done"]

### How It Works

All promises start at the same time

JavaScript waits for all to finish

Returns results in an array

 Order of results = order of promises (not completion time)

Example with Different Times

```js
const p1 = new Promise((resolve) =>
  setTimeout(() => resolve("First"), 2000)
);

const p2 = new Promise((resolve) =>
  setTimeout(() => resolve("Second"), 1000)
);

const p3 = new Promise((resolve) =>
  setTimeout(() => resolve("Third"), 3000)
);

Promise.all([p1, p2, p3])
  .then((results) => console.log(results));
```

Output

["First", "Second", "Third"]

Even though p2 finished first, order is maintained

Important Behavior: If One Fails 

If any promise fails, Promise.all() fails immediately

```js
const p1 = Promise.resolve("Success");
const p2 = Promise.reject("Error occurred");
const p3 = Promise.resolve("Another success");

Promise.all([p1, p2, p3])
  .then((res) => console.log(res))
  .catch((err) => console.log("Caught:", err));
```
Output

Caught: Error occurred

Other results are ignored

Example: Fetch multiple data

```js
const userPromise = fetch("/user");
const orderPromise = fetch("/orders");
const productPromise = fetch("/products");

Promise.all([userPromise, orderPromise, productPromise])
  .then(([user, orders, products]) => {
    console.log(user, orders, products);
  })
  .catch((err) => console.log(err));
```

## When to Use Promise.all()?

Use it when:

Tasks are independent

You want faster execution

You need all results together

## When NOT to Use?

Avoid when:

Tasks depend on each other

You want partial results (use Promise.allSettled() instead)

## Advantages

Fast execution 

Cleaner code

Easy to manage multiple results

## Disadvantages

Fails if one promise fails 

No partial results

## Summary

Promise.all() runs promises in parallel

Returns all results as an array

Maintains order of promises

Fails if any promise fails

Best for independent tasks