# Inversion of Control (IoC) in Callbacks 

## What is Inversion of Control?

Inversion of Control (IoC) means:
 You give control of your code to someone else.

Normally:
- You control when a function runs

With IoC:
- Someone else controls when your function runs


## Basic Example (Without IoC)

```javascript
function sayHello() {
  console.log("Hello");
}

sayHello(); // You control execution
```
- Here, YOU decide when to call the function.

## Example with IoC (Using Callback)

```js
function fetchData(callback) {
  console.log("Fetching data...");
  
  setTimeout(() => {
    callback("Data received");
  }, 2000);
}

fetchData((data) => {
  console.log(data);
});
```
 Here:

You give your function to fetchData

fetchData decides when to call it

 Control is inverted!

### Why is this called "Inversion"?

Because control is reversed:

Normal Flow	With IoC
You call function	Someone calls your function
You control flow	External code controls flow


## Problems with IoC in Callbacks

### 1. Loss of Control

You don’t know:

When your callback will run

If it will run

How many times it will run

### 2. Trust Issues

You are trusting another function:

doSomething(callback);

What if:

It never calls callback?

Calls it twice?

Calls it with wrong data?

### 3. Hard to Debug

When many callbacks are used:

Flow becomes confusing

Hard to track execution

Example Problem

```js
function doTask(callback) {
  // Unknown behavior
  callback("Done");
  callback("Done Again"); // Called twice!
}

doTask((msg) => {
  console.log(msg);
});
```
 Output:

Done
Done Again

Unexpected behavior!


## How to Solve IoC Problems?

### 1. Promises

Promises give control back to you:

```js
function fetchData() {
  return new Promise((resolve, reject) => {
    setTimeout(() => resolve("Data received"), 2000);
  });
}

fetchData().then(data => console.log(data));
```

 Promise guarantees:

Called once

Either success or failure

### 2. Async/Await

Cleaner and more controlled:

```js
async function process() {
  const data = await fetchData();
  console.log(data);
}
```
## Summary

IoC = Giving control to another function

Common in callbacks

Can cause trust and control issues

Solved using Promises and Async/Await