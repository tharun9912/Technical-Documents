# 📄 Reading Error Messages & Stack Traces (Simple Guide)

## 1. Introduction

When your code breaks, JavaScript shows an **error message**.

This message helps you understand:
-  What went wrong  
-  Where it went wrong  
-  How to fix it  

The most important part is the **stack trace**.

---

## 2. What is an Error Message?

An **error message** is a text shown by JavaScript when something fails.

### Example:
```js
console.log(x);
```

- ReferenceError: x is not defined is the error message in above program.

**Meaning:**

ReferenceError → Type of error

x is not defined → Problem

  You used a variable that doesn’t exist.


## 3. What is a Stack Trace?

A stack trace shows:
   - The path your code took before crashing

Think of it like:

  - “Which functions were called before the error happened?”

## 4. Simple Stack Trace Example

```js
function a() {
  b();
}

function b() {
  c();
}

function c() {
  console.log(x); // error here
}

a();
```

### output

```js
ReferenceError: x is not defined
    at c (func.js:10)
    at b (func.js:6)
    at a (func.js:2)
```

## 5. How to Read This

 - Start from top → bottom

     at c (app.js:10)  ❗ ERROR happened here
     at b (app.js:6)
     at a (app.js:2)

 Meaning:

    Error happened inside function c

    c was called by b

    b was called by a

## 6. Common Error Types

### 1. ReferenceError

```js
 console.log(x);
```
   Variable not declared

### 2. TypeError

```js
 let x = null;
 console.log(x.name);
 ```
   Accessing property of null/undefined

### 3. SyntaxError

  ```js
    if true 
   { 
  ```

## 7. Summary

Error message = what went wrong

Stack trace = where + how it happened

Always start from top of stack

Trace function calls backward

