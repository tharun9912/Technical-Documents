# Default Parameters in JavaScript 

 - Sometimes when we call a function, we don’t pass all arguments.
 -  This can cause problems like undefined values.
 - Default parameters solve this problem by:
    - Giving a default value if no argument is passed

 - Basic Syntax

```js
   function greet(name = "Guest") {
     console.log(`Hello ${name}`);
   }
  greet();        // no argument
  greet("John");  // with argument
```
Output:

Hello Guest
 
 Hello John

- If value is missing → default is used
- If value is given → it overrides default

## Why Default Parameters?

-  Without Default Parameters

```js
function greet(name) {
  console.log(`Hello ${name}`);
}

greet();
```
 Output: Hello undefined

- With Default Parameters

```js
function greet(name = "Guest") {
  console.log(`Hello ${name}`);
}

greet();
```

Output: Hello Guest

## Multiple Default Parameters

```js
function add(a = 0, b = 0) {
  return a + b;
}

console.log(add());       // 0
console.log(add(5));      // 5
console.log(add(5, 10));  // 15
```

## Default Parameters with Expressions

```js
function multiply(a, b = a * 2) {
  return b;
}

console.log(multiply(5));
```
 Output: 10

-  Default value can depend on another parameter

## Default Parameters with Functions

```js
function getValue() {
  return 100;
}

function print(value = getValue()) {
  console.log(value);
}

print();
```
 Output: 100

 
##  Passing undefined vs null

```js
function test(value = "Default") {
  console.log(value);
}

test(undefined);
test(null);
```

Output:
  
  Default
  
  null


**undefined → uses default**

**null → treated as value**

## When to Use Default Parameters

Use when:

- Function arguments may be missing

- You want fallback values

- Making functions safer

 - Writing clean APIs

## Summary

Default parameters provide fallback values

Avoid undefined errors.

Work with expressions and functions.

undefined triggers default, null does not.