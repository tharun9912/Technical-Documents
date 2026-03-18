# Debugging Strategies in JavaScript

Debugging means **finding and fixing errors (bugs)** in your code.

Every developer makes mistakes — debugging helps you solve them.


##  Use `console.log()`

This is the simplest way to debug.

### Example

```javascript
let a = 5;
let b = 10;

console.log(a);
console.log(b);
console.log(a + b);
```
Use Case

Check variable values

Track program flow

## Read Error Messages Carefully

JavaScript gives error messages in the console.

Example Error
```js
console.log(x);
```
Output :  ReferenceError: x is not defined
Tip

Always read the error message

It tells what went wrong and where

## Use Browser DevTools

Open DevTools:

Right click → Inspect → Console / Sources

Features

Console for logs

Breakpoints to pause code

Step-by-step execution

## Use Breakpoints

Breakpoints pause your code at a specific line.

Steps

Open DevTools → Sources

Click line number


## Use try...catch

Handle errors safely.

Example
```js
try {
    let result = x + 10;
} catch (error) {
    console.log("Error:", error.message);
}
```
## Simplify Your Code

Break large code into small parts.

Bad
```js
let result = (a + b) * (c - d) / e;
```

Better
```js
let sum = a + b;
let diff = c - d;
let result = sum * diff / e;
```
## Test with Different Inputs

Try different values to find bugs.

Example
```js
function divide(a, b) {
    return a / b;
}

console.log(divide(10, 2));
console.log(divide(10, 0)); // edge case
```

## Use Linting Tools

Tools like ESLint help find mistakes before running code.

##  Rubber Duck Debugging 

Explain your code step by step (even to yourself).

Helps you find mistakes quickly

Makes logic clear

## Summary

Debugging is an important skill.

Key Tips:

Use console.log

Read errors carefully

Use DevTools

Break code into smaller parts