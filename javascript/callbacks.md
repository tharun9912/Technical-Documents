# Passing Functions to Other Functions (Callbacks) in JavaScript

In JavaScript, functions are treated like **values**. 
This means: 
  - You can store them in variables
 -  You can pass them to other functions 
 -  You can return them from other functions

When we pass a function to another function and execute it later, it is
called a **callback function**.

## Why Do We Use This?

We use this concept when: 
  - We want to **delay execution** 
  - We want to make code **flexible and reusable** 
  - We handle **events, timers, or async operations**


## Basic Example

``` javascript
function greet(name) {
    console.log("Hello " + name);
}

function User(callback) {
    const name = "Tharun";
    callback(name); // invoking the function
}

User(greet);
```

### Output:

    Hello Tharun

### Explanation:

-   `greet` is passed as a function
-   `User` calls it when needed

## Example 3: Anonymous Function

``` javascript
function process(callback) {
    callback();
}

process(function() {
    console.log("This runs on demand");
});
```

------------------------------------------------------------------------

## Example 4: Using Arrow Functions

``` javascript
function process(callback) {
    callback();
}

process(() => {
    console.log("Arrow function executed");
});
```

## Key Concepts

-   Functions can be passed like variables
-   A function passed to another is called a **callback**
-   Execution happens only when it is **invoked**

------------------------------------------------------------------------

## Advantages

-   Code becomes reusable
-   Helps in asynchronous programming
-   Makes programs more flexible


## Summary

Passing functions to other functions allows us to control **when and how
code runs**.\
It is a core concept in JavaScript and widely used in: - Event
handling - APIs - Timers - Functional programming