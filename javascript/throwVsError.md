# Difference Between `throw new Error()` and `throw "string"` in JavaScript

## What is `throw`?

`throw` is used to **create (throw) an error** in JavaScript.

```js
throw "Something went wrong";
```

---

## 1. throw "Error message" (Throwing a String)

You can throw a simple string.

### Example

```js
function checkAge(age) {
  if (age < 18) {
    throw "Too young";
  }
  return "Access granted";
}

try {
  checkAge(15);
} catch (error) {
  console.log(error); // Too young
}
```

### Problem

- It is just a **string**
- No extra information (like error type, stack trace)
- Harder to debug in real projects

---

## 2. throw new Error("Error message") (Recommended)

This creates a **proper Error object**.

### Example

```js
function checkAge(age) {
  if (age < 18) {
    throw new Error("Too young");
  }
  return "Access granted";
}

try {
  checkAge(15);
} catch (error) {
  console.log(error.message); // Too young
}
```

---

## Why `Error` is Better?

`Error` object gives extra information:

- `message` → error message
- `name` → type of error
- `stack` → where error happened

### Example

```js
try {
  throw new Error("Something broke");
} catch (error) {
  console.log(error.name);    // Error
  console.log(error.message); // Something broke
}
```

---

## Key Differences

| Feature | throw "string" | throw new Error() |
|--------|----------------|-------------------|
| Type | String | Error object |
| Debugging | ❌ Hard | ✅ Easy |
| Stack trace | ❌ No | ✅ Yes |
| Professional use | ❌ Not recommended | ✅ Recommended |

---

## Simple Analogy

- `throw "error"` → just sending a **message**
- `throw new Error()` → sending a **full report**

---

## When to Use

- Use `throw new Error()` in **real projects**
- Avoid throwing plain strings

---

## Summary

- `throw "message"` → simple but limited
- `throw new Error("message")` → powerful and recommended
- Always use `Error` for better debugging and clean code