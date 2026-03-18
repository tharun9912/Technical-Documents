#  Console Methods in JavaScript 

The `console` object in JavaScript is used for:
 Printing messages  
 Debugging code  
 Checking values  

It provides different methods like:
- console.log()
- console.error()
- console.info()
- console.warn()
- console.table()
- console.time() / console.timeEnd()

---

## console.log()

 Used to print general messages

```js
console.log("Hello World");
```
Shows message (in browsers)

##  console.error()

Used to print error messages

```js
console.error("Something went wrong");
```

## console.info()

 Used for informational messages

```js
console.info("This is info message");
```
 Similar to console.log() but used for info

## console.warn()

 Used for warnings

```js
console.warn("This is a warning");
```
 Shows message in yellow color.

## console.table()

 Displays data in table format

```js
let users = [
  { name: "John", age: 25 },
  { name: "Alice", age: 30 }
];

console.table(users);
```
 Output shown as table (in browser console)

## console.time() and console.timeEnd()

 Used to measure execution time

```js
console.time("timer");
for (let i = 0; i < 1000000; i++) {}
console.timeEnd("timer");
```
 Output:  timer: 5ms

## console.clear()

Clears the console

```js
console.clear();
```
## console.group()

 Groups messages together

```js
console.group("User Info");
```
## console.assert()

 Checks condition

```js
console.assert(3 > 4, "Condition is false");
```
 Prints message only if condition is false
