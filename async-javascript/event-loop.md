# Event Loop in JavaScript 

## What is the Event Loop?

The Event Loop is a mechanism in JavaScript that allows it to handle asynchronous operations (like API calls, timers, etc.) even though JavaScript is single-threaded.

JavaScript can do only one thing at a time, but the Event Loop helps it handle multiple tasks without blocking the main thread.

---

## Why Do We Need Event Loop?

JavaScript runs in a single thread, meaning:
- It can execute only one line at a time
- Long tasks can block the entire program

The Event Loop solves this problem by:
- Moving time-consuming tasks outside the main thread
- Bringing results back when they are ready

---

## Key Components

### 1. Call Stack

- Where JavaScript executes code
- Works in LIFO (Last In First Out)

Example:

```javascript
function a() {
  console.log("A");
}
function b() {
  a();
}
b();
```
Execution:

b() pushed → calls a() → prints "A"

### 2. Web APIs (Browser APIs)

Provided by the browser

Handle async tasks like:

setTimeout

fetch

DOM events

### 3. Callback Queue

Stores callback functions after async tasks are completed

### 4. Event Loop

Constantly checks:
 "Is Call Stack empty?"

If yes, it pushes tasks from Callback Queue to Call Stack

How Event Loop Works (Step-by-Step)

Example:

```js
console.log("Start");

setTimeout(() => {
  console.log("Inside Timeout");
}, 0);

console.log("End");
```
Execution Flow:

console.log("Start") → runs immediately

setTimeout → moved to Web API

console.log("End") → runs

Timer completes → callback goes to Queue

Event Loop moves it to Call Stack

"Inside Timeout" gets printed

Output:
Start
End
Inside Timeout

Even if delay is 0 ms:

setTimeout(() => {
  console.log("Hello");
}, 0);

  - It will NOT run immediately
  - It runs after the Call Stack is empty

## Microtask Queue vs Callback Queue

There are two queues:

### 1. Microtask Queue (High Priority)

Promise callbacks

MutationObserver

Example:

```js
Promise.resolve().then(() => console.log("Promise"));
```
### 2. Callback Queue (Low Priority)

setTimeout

setInterval

Example:
```js
console.log("Start");

setTimeout(() => console.log("Timeout"), 0);

Promise.resolve().then(() => console.log("Promise"));

console.log("End");
```
Output:
Start
End
Promise
Timeout

 Because Microtasks run before normal callbacks

## SUmmary

The Event Loop makes JavaScript powerful by:

Handling async operations

Preventing blocking

Managing execution order