# What Happens When a Function Does Not Have a Return Statement?

- In many languages like JavaScript, Python, etc., a function can run without a `return`.

## What happens?

When a function does not have a `return` statement:
- The function still runs its code
- But it gives back a default value
- This default is usually `undefined` in JavaScript.

## Simple Example

### JavaScript
```js
function sayHello(name) {
  console.log("Hello " + name);
}

let result = sayHello("Alice");
console.log(result); // undefined
```

## Summary

- Function returns undefined if it does not have a return statement.

- It won't give any error. 