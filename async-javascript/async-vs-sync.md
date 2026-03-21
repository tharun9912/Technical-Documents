# Difference Between Synchronous and Asynchronous JavaScript


In JavaScript, code can run in two ways:
- **Synchronous (Sync)**
- **Asynchronous (Async)**


##  Synchronous (Sync)

Synchronous means:
  - Code runs **line by line**, one after another  
  - Each task waits for the previous one to finish

### Example:
```js
console.log("1");
console.log("2");
console.log("3");
```

### Output:
```
1
2
3
```
 Here, each line waits for the previous one


##  Problem with Sync

If a task takes long time, everything stops.

### Example:
```js
console.log("Start");

for (let i = 0; i < 1e45; i++) {
  // heavy task takes long time
}

console.log("End");
```

 "End" will be delayed because loop blocks execution


##  Asynchronous (Async)

Asynchronous means:
 -  Code does NOT wait  
 - Long tasks run in background  
 - Other code continues execution

### Example:
```js
console.log("Start");

setTimeout(() => {
  console.log("Inside Timeout");
}, 2000);

console.log("End");
```

### Output:
```
Start
End
Inside Timeout
```

 JS does not wait for setTimeout

---

##  How Async Works (Simple)

1. Async task goes to **Web APIs**
2. After completion → moves to **Callback Queue**
3. **Event Loop** pushes it to Call Stack when empty

---

##  Difference Table

| Feature        | Synchronous (Sync)        | Asynchronous (Async)        |
|----------------|--------------------------|-----------------------------|
| Execution      | Line by line             | Does not wait               |
| Blocking       | Blocking                 | Non-blocking                |
| Speed          | Slower for heavy tasks   | Faster for real apps        |
| Use case       | Simple logic             | API calls, timers, events   |

---


##  When to Use

Use Sync:
- Simple calculations
- Small tasks

Use Async:
- API calls
- File reading
- Timers
- Database queries


##  Summary

- Sync = step by step, blocking
- Async = non-blocking, runs in background
- JS uses **event loop** to manage async

