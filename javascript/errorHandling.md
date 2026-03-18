# Error Handling in JavaScript (try...catch)

## What is Error Handling?

Error handling means **handling problems in code** so that the program does not crash.

Sometimes, errors happen like:
- wrong input
- undefined variables
- API failures

We use `try...catch` to handle these errors safely.

---

## Basic Syntax

```js
try {
  // code that may cause error
} catch (error) {
  // code to handle error
}
```

---

## Simple Example

```js
try {
  let result = x + 10; // x is not defined
} catch (error) {
  console.log("Error occurred");
}
```

Output:
```
Error occurred
```

Explanation:
- `try` block runs code
- error happens
- control goes to `catch`

---

## Using Error Object

```js
try {
  let result = x + 10;
} catch (error) {
  console.log(error.message);
}
```

Output:
```
x is not defined
```

---

## try...catch with finally

`finally` always runs, whether error happens or not.

```js
try {
  console.log("Try block");
} catch (error) {
  console.log("Catch block");
} finally {
  console.log("Finally block");
}
```

Output:
```
Try block
Finally block
```

---

## Throwing Custom Errors

You can create your own errors using `throw`.

```js
function checkAge(age) {
  if (age < 18) {
    throw "You are too young";
  }
  return "Access granted";
}

try {
  console.log(checkAge(15));
} catch (error) {
  console.log(error);
}
```

Output:
```
You are too young
```

---

## When to Use try...catch

Use it when:
- code may fail (API calls, JSON parsing)
- working with user input
- handling runtime errors

---

## Important Notes

- `try...catch` works only for **runtime errors**
- It does not catch syntax errors.

---

## Summary

-  Use try to run risky code.
- Use catch for handling error. 
- Finally to run every time.
- Throw to create custom errors.
- Error handling helps make programs **safe and stable**.