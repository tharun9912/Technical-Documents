# Truthy and Falsy Values in JavaScript

## Introduction

In JavaScript, every value is either **truthy** or **falsy** when used
in a condition.

### Falsy Values

Falsy values behave like `false` in conditions.

Common falsy values:
   - false 
   -  0 
   -  "" (empty string) 
   -  null 
undefined - NaN

### Example

``` javascript
let value = 0;

if(value){
  console.log("Truthy");
}else{
  console.log("Falsy");
}
```

Output:

    Falsy

### Truthy Values

All values that are not falsy are considered **truthy**.

Examples: 

- "hello" 
- 10 -
-  \[\] 
-  {} 
-  true

Example:

``` javascript
let name = "Tharun";

if(name){
  console.log("Value exists");
}
```

### Summary

- false,null,undefined,empty string are falsy values.

- Except falsy values, remaining things are  truthy values.
