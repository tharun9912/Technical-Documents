#  Error Handling in JavaScript

# Introduction

Error handling ensures that your application: 
 - Does not crash unexpectedly 
 - Handles failures gracefully 
 - Provides useful debugging information


# Types of Errors

## Syntax Error

- Occurs when code is invalid.
- Syntax errors happen in the parsing/compilation phase, before the code even runs.

``` javascript
let a = ; // Syntax Error
```

## Runtime Error

Occurs during execution.

``` javascript
console.log(x); // ReferenceError
```

## Logical Error

Code runs but gives wrong result.

``` javascript
console.log(4 + "5"); // "45"
```


#  try...catch

``` javascript
try {
  let x=;
} catch (error) {
  console.log(error.message);
}
```

### Flow:

1.  try block executes
2.  If error → jump to catch
3.  catch handles error


#  try...catch...finally

``` javascript
try {
  console.log("Try block");
} catch (e) {
  console.log("Error");
} finally {
  console.log("Always runs");
}
 ```


#  Throwing Errors

``` javascript
function withdraw(balance, amount) {
  if (amount > balance) {
    throw new Error("Insufficient balance");
  }
}
```

# throw new Error vs throw string

  - Both throw new Error() and throwing a string can provide an error message.
  
  - Using throw new Error() includes a stack trace, whereas throwing a string does not include a stack trace.
 
 - Debugging is easier when using throw new Error() because it provides structured information, while debugging is harder when throwing a string due to the lack of detailed error information.


## Error object

``` javascript
try {
  throw new Error("Something broke");
} catch (e) {
  console.log(e.name);    // Error
  console.log(e.message); // Something broke
  console.log(e.stack);   // stack trace
}
```

## error string 

```js
try {
  throw "Login failed";
} catch (e) {
  console.log(e);        // Login failed
  console.log(e.stack);  // undefined 
}
```

#  Stack Trace 

``` javascript
function a() { b(); }
function b() { c(); }
function c() { throw new Error("Crash"); }

a();
```

Output:

    Error: Crash
     at c
     at b
     at a

### How to read:

-   Error starts at function `c`
-   Called by `b`
-   Called by `a`



#  Importance of catch block

## Prevent crash

``` javascript
try {
  risky();
} catch(e) {
  console.log("Handled");
}
```

## User-friendly message

``` javascript
catch(e) {
  console.log("Something went wrong");
}
```

## Debugging

``` javascript
catch(e) {
  console.log(e.stack);
}
```

#  Async Error Handling

## Using Promise

```js
function fetchData(success) {
  return new Promise((resolve, reject) => {
    if (success) {
      resolve("Data fetched successfully");
    } else {
      reject("Failed to fetch data");
    }
  });
}
```

### using error object

```js
function fetchData(success) {
  return new Promise((resolve, reject) => {
    if (success) {
      resolve("Data fetched successfully");
    } else {
      reject(new Error("Failed to fetch data"));
    }
  });
}

fetchData(false)
  .then((result) => {
    console.log(result);
  })
  .catch((error) => {
    console.log(error.message);
  });
```



## Using async/await

``` javascript
async function getData() {
  try {
    let res = await fetch("wrong-url");
  } catch (e) {
    console.log(e.message);
  }
}
```


#  Common Mistakes

 Ignoring errors
 Throwing strings
 Empty catch blocks

``` javascript
try {
  doSomething();
} catch(e) {} // bad
```


#  Best Practices

 - Always use `new Error()`
  
 - Log errors properly
 
 - Show user-friendly messages
 
 - Avoid swallowing errors
 
 - Use finally for cleanup


# Summary

- The try block is used to write code that may produce an error.
- The catch block is used to handle errors when they occur.
- The throw statement is used to create and raise custom errors.
- The finally block is used to execute code that will always run,  regardless of whether an error occurs or not.

- The stack trace helps in debugging by showing where the error occurred and the sequence of function calls that led to it.