#  Closures in JavaScript 


A **closure** is a concept where:
  -  A function remembers variables from its outer scope even after the outer function has finished execution.

---

## 2. Basic Example

```js
function outer() {
  let message = "Hello";

  function inner() {
    console.log(message);
  }

  return inner;
}

let fn = outer();
fn();
```

output:  Hello

## Why Closures Work

Functions in JavaScript can be returned

Functions keep access to their lexical scope

This creates a closure

- Closures help create private variables


```js
function createUser() {
  let password = "12345";

  return {
    checkPassword(input) {
      return input === password;
    }
  };
}

let user = createUser();

console.log(user.checkPassword("12345")); // true
```
 password cannot be accessed directly


 ## When to Use Closures

    Use closures when:
       - You need data privacy

       - You want to maintain state

       - Creating functions with memory

       - Callbacks and event handlers

##  Summary

Closure = function + its memory

Inner function remembers outer variables

Used for privacy and state

