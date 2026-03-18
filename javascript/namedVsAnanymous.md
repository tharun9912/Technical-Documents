# Named Functions vs Anonymous Functions in JavaScript.

In JavaScript, functions can be created in different ways. Two common
types are: - **Named Functions** - **Anonymous Functions**


## 1. Named Functions

A **named function** is a function that has a name.

### Syntax

``` javascript
function greet() {
    console.log("Hello");
}
```

### Example

``` javascript
function add(a, b) {
    return a + b;
}

console.log(add(2, 3));
```

### Output:

    5

### Key Points

-   Has a name (`add`, `greet`)
-   Can be reused multiple times
-   Easier to debug (name appears in error messages)
-   Supports **hoisting**


## 2. Anonymous Functions

An **anonymous function** is a function without a name.

### Syntax

``` javascript
const greet = function() {
    console.log("Hello");
};
```

### Example

``` javascript
const add = function(a, b) {
    return a + b;
};

console.log(add(2, 3));
```

### Output:

    5

### Key Points

-   No function name
-   Usually stored in a variable
-   Used in callbacks and one-time use cases
-   Not hoisted like named functions


## 3. Key Differences

  Feature       Named Function    Anonymous Function
  ------------- ----------------- -------------------------
  Name          Has a name        No name
  Reusability   High              Usually used once
  Hoisting      Yes               No
  Debugging     Easy              Harder
  Usage         General purpose   Callbacks, inline logic



## 4. Example: Callback Comparison

### Named Function

``` javascript
function sayHello() {
    console.log("Hello");
}

setTimeout(sayHello, 1000);
```

### Anonymous Function

``` javascript
setTimeout(function() {
    console.log("Hello");
}, 1000);
```

##  Arrow Function (Modern Anonymous Function)

``` javascript
setTimeout(() => {
    console.log("Hello");
}, 1000);
```

##  When to Use What?

### Use Named Functions When:

-   You need to reuse the function
-   You want better debugging
-   Logic is complex

### Use Anonymous Functions When:

-   Function is used only once
-   Working with callbacks
-   Writing short, simple logic

## Conclusion

-   Named functions are **reusable and easier to debug**
-   Anonymous functions are **flexible and useful for quick tasks**
-   Both are important in JavaScript and used in different situations