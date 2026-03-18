# Variable Number of Arguments in JavaScript Functions

Sometimes we don't know how many arguments will be passed to a
function.\
JavaScript allows us to handle this using:

-   `arguments` object (older way)
-   Rest parameters (`...args`) (modern way)


##  Using the `arguments` Object

The `arguments` object is available inside every regular function.

### Example

``` javascript
function sum() {
    let total = 0;
    for (let i = 0; i < arguments.length; i++) {
        total += arguments[i];
    }
    return total;
}

console.log(sum(1, 2, 3, 4));
```

### Output:

    10

### Explanation

-   `arguments` holds all passed values
-   It works like an array (but not exactly an array)


##  Using Rest Parameters (`...args`)

This is the modern and recommended way.

### Syntax

``` javascript
function functionName(...args) {
    // args is an array
}
```

### Example

``` javascript
function sum(...numbers) {
    return numbers.reduce((total, num) => total + num, 0);
}

console.log(sum(1, 2, 3, 4));
```

### Output:

    10

### Explanation

-   `...numbers` collects all arguments into an array
-   Easier to use than `arguments`


##  Example: Finding Maximum Number

``` javascript
function findMax(...nums) {
    return Math.max(...nums);
}

console.log(findMax(10, 20, 5, 30));
```

### Output:

    30


##  Important Notes

-   `arguments` is not available in arrow functions
-   Rest parameters must be the **last parameter**
-   You can mix fixed and variable arguments

### Example

``` javascript
function greet(message, ...names) {
    names.forEach(name => {
        console.log(message + " " + name);
    });
}

greet("Hello", "John", "Sam", "Alex");
```

## Summary

Handling variable arguments makes your functions: - Flexible -
Reusable - Powerful

Use **rest parameters (`...args`)** in modern JavaScript for cleaner and
better code.