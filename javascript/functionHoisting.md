# Function Hoisting in JavaScript

## Introduction

- Hoisting means JavaScript **moves function declarations to the top of
the scope before execution**.

### Example

``` javascript
greet();

function greet(){
  console.log("Hello");
}
```

Output:

    Hello

### Why it Works

- JavaScript internally treats it like this:

``` javascript
function greet(){
  console.log("Hello");
}

greet();
```

### Function Expressions Are Not Hoisted

``` javascript
greet();

const greet = function(){
  console.log("Hello");
}
```

- This will cause an **error** because function expressions are not
hoisted.

### Arrow Functions Are Not Hoisted

```javascript
sayHello(); //  ReferenceError: Cannot access 'sayHello' before initialization

const sayHello = () => {
  console.log("Hello!");
};
```

- Arrow functions are usually assigned to a const or let variable.

- Only the variable name is hoisted (like let/const), not the function itself.

 - So calling it before definition causes an error.

### Summary

- Only functions declared using function definitions are hoisted.

- Function expressions won't support hoisting.

- Arrow functions won't support hoisting.