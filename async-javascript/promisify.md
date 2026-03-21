# Promisifying Callback-Based Functions 

## What is Promisification?

Promisification means converting a callback-based function into a promise-based function.


## Why Do We Need Promisification?

Callback-based code:
- Hard to read 
- Leads to callback hell
- Difficult error handling

Promise-based code:
- Cleaner 
- Easier to manage
- Better error handling

## Basic Idea

### Callback Style

```javascript
function doTask(callback) {
  setTimeout(() => {
    callback("Task done");
  }, 1000);
}
```
Promise Style

```js
function doTaskPromise() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve("Task done");
    }, 1000);
  });
}
```

## 1. Promisifying setTimeout

### Callback Version
```js
setTimeout(() => {
  console.log("Hello");
}, 1000);
```

### Promisified Version

```js
function delay(ms) {
  return new Promise((resolve) => {
    setTimeout(resolve, ms);
  });
}

delay(1000).then(() => {
  console.log("Hello after 1 second");
});
```

### 2. Promisifying fs.readFile (Node.js)

### Callback Version

```js
const fs = require("fs");

fs.readFile("file.txt", "utf8", (err, data) => {
  if (err) {
    console.log(err);
  } else {
    console.log(data);
  }
});
```

### Promisified Version

```js
const fs = require("fs");

function readFilePromise(path) {
  return new Promise((resolve, reject) => {
    fs.readFile(path, "utf8", (err, data) => {
      if (err) {
        reject(err);
      } else {
        resolve(data);
      }
    });
  });
}

readFilePromise("file.txt")
  .then((data) => console.log(data))
  .catch((err) => console.log(err));
```

## 3. General Pattern for Promisification

 ### Most callback functions follow this pattern:

      callback(error, result);

Convert it like this:

```js
function promisifiedFunction() {
  return new Promise((resolve, reject) => {
    originalFunction((err, result) => {
      if (err) {
        reject(err);
      } else {
        resolve(result);
      }
    });
  });
}
```
## 4. Using util.promisify (Node.js Built-in)

Node.js provides a helper:

```js
const fs = require("fs");
const util = require("util");

const readFilePromise = util.promisify(fs.readFile);

readFilePromise("file.txt", "utf8")
  .then(console.log)
  .catch(console.error);
```

## 5. Using Async/Await 

```js
async function readFileData() {
  try {
    const data = await readFilePromise("file.txt");
    console.log(data);
  } catch (err) {
    console.log(err);
  }
}
```

Callback:

You give your number and wait for a call 

Promise:

You get a tracking system with clear status 

## Advantages of Promisification

Cleaner code

Avoids callback hell

Better error handling

Works with async/await

## Summary

Promisification = converting callbacks to promises

Wrap callback inside new promise

Use resolve and reject

Use util.promisify in Node.js

Prefer async/await for cleaner code