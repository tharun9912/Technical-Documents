#  Arrow Functions vs Regular Functions in JavaScript

## 1. Introduction

JavaScript has two ways to write functions:
- Regular Functions  
- Arrow Functions  

Both are used to write reusable code, but they behave differently in some cases.

---

## 2. Syntax Difference

### Regular Function
```js
function greet(name) {
  return "Hello " + name;
}
```

### Arrow Function

```js
const greet = (name) => {
  return `Hello ${name}`;
};
```

## Short Syntax (Arrow Function)
```js
const greet = name => `Hello ${name}`;
```
  No need for return if single line

## this Keyword Difference (Very Important)

### Regular Function
```js
const user = {
  name: "tarun",
  greet: function () {
    console.log(this.name);
  }
};

user.greet();
```

 Output: tarun

### Arrow Function

```js
const user = {
  name: "John",
  greet: () => {
    console.log(this.name);
  }
};

user.greet();
```
 Output:  undefined

- Arrow function does NOT have its own this
- It takes this from outer scope

## Arguments Object

### Regular Function
```js
function show() {
  console.log(arguments);
}

show(1, 2, 3);
```
it  Works 

### Arrow Function

```js
const show = () => {
  console.log(arguments);
};

show(1, 2, 3);
```
- Error because arrow functions don’t have arguments.

##   Constructor Function

### Regular Function

```js
function Person(name) {
  this.name = name;
}

let p = new Person("John");
```
-  Works 

### Arrow Function
```js
const Person = (name) => {
  this.name = name;
};

let p = new Person("John");
```
Error,arrow functions cannot be used with new

## Hoisting

### Regular Function

```js
greet();
function greet() {
  console.log("Hello");
}
```
 Works (hoisted)

### Arrow Function

```js
greet();

const greet = () => {
  console.log("Hello");
};
```
 Error  (not hoisted like regular functions)

## When to Use What

### Use Arrow Functions when:

Writing short functions

Callbacks (map, filter, reduce)

You don’t need this

### Use Regular Functions when:

Working with objects and this

Constructor functions

Need arguments

Need hoisting

