#  Importing & Exporting Modules using require and module.exports 

In Node.js, we often split code into multiple files.

-  This is called **modular programming**

To share code between files, we use:

- `module.exports` → to export  
- `require()` → to import  

---

## 2. What is a Module?

  A module is simply a file.

Example:
- `math.js`

---

## 3. Exporting using module.exports

  Used to send data or functions from one file

### Example: math.js

```js
function add(a, b) {
  return a + b;
}

module.exports = add;
```

## Importing using require()

 Used to receive data from another file

Example: app.js
```js
const add = require("./math");
console.log(add(2, 3));
```
Output: 5

## Exporting Multiple Values

math.js

```js
function add(a, b) {
  return a + b;
}

function subtract(a, b) {
  return a - b;
}

module.exports = {
  add,
  subtract
};
```
app.js
```js
const math = require("./math");
console.log(math.add(2, 1));
console.log(math.subtract(2, 1));
```
Output:
3
1

## Destructuring Import


```js
  const { add, subtract } = require("./math");
  console.log(add(10, 5));
```


##  Exporting One by One

```js
exports.add = function(a, b) {
  return a + b;
};

exports.sub = function(a, b) {
  return a - b;
};
```
 exports is shortcut of module.exports


##   When to Use

Use modules when:

   - Code is large

   - Reusing functions


##  Summary

module.exports → export code

require() → import code

Helps organize and reuse code

