# Consuming Multiple Promises by Chaining 

## What is Promise Chaining?

Promise chaining means executing multiple asynchronous tasks one after another using `.then()`.


## Why Use Chaining?

We use chaining when:
- Tasks depend on each other
- Output of one task is needed for the next

## Basic Idea

```javascript
task1()
  .then(result1 => task2(result1))
  .then(result2 => task3(result2))
  .then(result3 => console.log(result3));
```

Each step:

Waits for previous task

Uses its result

```js
function step1() {
  return new Promise((resolve) => {
    setTimeout(() => resolve(10), 1000);
  });
}

function step2(num) {
  return new Promise((resolve) => {
    setTimeout(() => resolve(num * 2), 1000);
  });
}

step1()
  .then((res1) => {
    console.log("Step 1:", res1);
    return step2(res1);
  })
  .then((res2) => {
    console.log("Step 2:", res2);
    return step3(res2);
  })
  .catch((err) => console.log(err));
```

Output

Step 1: 10

Step 2: 20

Important Rule

 Always return the next promise inside .then()

```js
step1().then((res) => {
  return step2(res); // Returned properly
});
```

Works only if:

Each function returns a promise

Each takes one argument


## Error Handling in Chaining

```js
step1()
  .then((res) => {
    throw new Error("Something failed!");
  })
  .then(step2) //  Skipped
  .catch((err) => {
    console.log("Caught:", err.message);
  });
```

If any step fails:

 Remaining .then() are skipped

 .catch() handles error

## When to Use Chaining?

Use chaining when:

Tasks depend on previous results

Order of execution matters

## Summary

Promise chaining = sequential execution

Each .then() waits for previous

Always return promise inside .then()

Errors are handled by .catch()