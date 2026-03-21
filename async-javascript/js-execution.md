# How JavaScript Executes Code (Simple Technical Paper)

JavaScript (JS) is a **single-threaded, synchronous language**, but it can handle asynchronous tasks using special mechanisms like the **event loop**.

To understand how JS runs code, we need to learn these main concepts:
- Execution Context
- Call Stack
- Memory Heap
- Event Loop
- Callback Queue

---

##  Execution Context

Execution context is the **environment where JavaScript code is executed**.

There are 2 types:
1. **Global Execution Context (GEC)** – runs first
2. **Function Execution Context (FEC)** – created when a function is called

### Example:
```js
var x = 5;

function greet() {
  console.log("Hello");
}

greet();
```

### What happens:
1. Global execution context is created
2. `x` and `greet` are stored in memory
3. `greet()` is called → new execution context is created

---

##  Memory Creation Phase & Execution Phase

Each execution context has 2 phases:

### 1. Memory Creation Phase
- Variables are stored with value `undefined`
- Functions are stored completely

### 2. Execution Phase
- Code runs line by line
- Values are assigned

### Example:
```js
console.log(a);
var a = 5;
```

### Output:
```
undefined
```

 Because:
- Memory phase: `a = undefined`
- Execution phase: `a = 5`

This behavior is called **Hoisting**

---

##  Call Stack

Call Stack is where JS keeps track of function execution.

It follows **LIFO (Last In First Out)**

### Example:
```js
function one() {
  two();
}

function two() {
  console.log("Inside two");
}

one();
```

### Execution Flow:
1. Global context pushed
2. `one()` pushed
3. `two()` pushed
4. `two()` executed → popped
5. `one()` popped

---

##  Memory Heap

- Stores objects and variables
- Works with call stack

### Example:
```js
let obj = { name: "Tharun" };
```

 Object is stored in **heap memory**, reference in stack

---

##  Asynchronous JavaScript

JS can handle async tasks like:
- `setTimeout`
- API calls
- Events

### Example:
```js
console.log("Start");

setTimeout(() => {
  console.log("Inside timeout");
}, 2000);

console.log("End");
```

### Output:
```
Start
End
Inside timeout
```

 Because `setTimeout` is handled outside JS (Web APIs)


##  Event Loop & Callback Queue

### How async works:

1. `setTimeout` goes to **Web API**
2. After time, callback goes to **Callback Queue**
3. Event Loop checks:
   - If call stack is empty → moves callback to stack


##   Complete Example

```js
console.log("A");

setTimeout(() => {
  console.log("B");
}, 1000);

console.log("C");
```

### Output:
```
A
C
B
```

 Even with `0ms`, it goes through event loop



##  Summary

- JS runs in a **single thread**
- Uses **Execution Context** to run code
- **Call Stack** manages function calls
- **Heap** stores objects
- **Event Loop + Callback Queue** handle async tasks

