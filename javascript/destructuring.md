#  Destructuring in JavaScript 


**Destructuring** is a way to:
👉 Extract values from arrays or objects easily

It makes code:
- Cleaner 
- Shorter   
- Easy to read   

---

## 2. Destructuring Arrays

### Basic Example

```js
let arr = [1, 2, 3];

let [a, b, c] = arr;

console.log(a, b, c);
```
output : 1 2 3

- Values are assigned based on position

## Skipping Values

```js
let arr = [1, 2, 3];

let [a, , c] = arr;

console.log(a, c);
```

Output:  1 3

##  Default Values

```js
let arr = [1];

let [a, b = 10] = arr;

console.log(a, b);
```

Output: 1 10

 Default is used if value is missing

##  Destructuring Objects

Basic Example

```js
let user = {
  name: "John",
  age: 25
};

let { name, age } = user;

console.log(name, age);
```
Output: John 25

## Default Values in Objects
```js
let user = {
  name: "John"
};

let { name, age = 30 } = user;

console.log(name, age);
```
Output:
John   30

## Nested Destructuring

```js
let user = {
  name: "Tharun",
  address: {
    city: "Bangalore"
  }
};

let { address: { city } } = user;

console.log(city);
```

Output:
Bangalore

## Destructuring in Function Parameters

```js
function printUser({ name, age }) {
  console.log(name, age);
}

printUser({ name: "Tarun", age: 23 });
```
Directly extract values from object

## Array Destructuring with Rest

```js
let arr = [1, 2, 3, 4];

let [a, ...rest] = arr;

console.log(a, rest);
```

Output:
1 [2, 3, 4]

##  When to Use Destructuring

Use when:

  - Working with objects (APIs)
  - Extracting multiple values
  - Cleaner function parameters


##  Summary

Destructuring extracts values easily

Works with arrays and objects

Supports default values

Makes code clean and readable