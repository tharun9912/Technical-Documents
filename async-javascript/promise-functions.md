#  Promise Utility Methods in JavaScript

##  1. Promise.resolve()

Creates a **resolved (fulfilled) promise immediately**.

###  When to use
- When you already have a value and want to wrap it inside a promise
- Useful in async functions or chaining

###  Example

```javascript
const p = Promise.resolve(10);

p.then(value => {
  console.log(value); // 10
});
```
####  Insight

Even if you pass a normal value, it becomes a promise:

Promise.resolve("Hello")

##  2. Promise.reject() 

Creates a rejected promise immediately.

### When to use

To simulate errors

To manually trigger failure in async flows

Example
```js
const p = Promise.reject("Error occurred");

p.catch(err => {
  console.log(err); // Error occurred
});
```

## 3. Promise.all()

Runs multiple promises in parallel and:

 Resolves when ALL succeed
 Rejects if ANY one fails

 Think of it as: “All must pass”

Example

```js
const p1 = Promise.resolve(1);
const p2 = Promise.resolve(2);
const p3 = Promise.resolve(3);

Promise.all([p1, p2, p3])
  .then(values => {
    console.log(values); // [1, 2, 3]
  });
```

Failure Case

```js
const p1 = Promise.resolve(1);
const p2 = Promise.reject("Failed");

Promise.all([p1, p2])
  .catch(err => {
    console.log(err); // Failed
  });
```

Key Point :  Stops at first rejection
 
 
## 4. Promise.allSettled()


Waits for all promises to finish, regardless of success or failure.

 Think of it as:

 “I want results of everything, no matter what”

 Example
```js
const p1 = Promise.resolve(1);
const p2 = Promise.reject("Error");

Promise.allSettled([p1, p2])
  .then(results => {
    console.log(results);
  });
```

 Output
[
  { status: "fulfilled", value: 1 },
  { status: "rejected", reason: "Error" }
]
 
## 5. Promise.any()


Returns the first successful (fulfilled) promise

Ignores failures 

Only fails if ALL promises fail

 Think of it as:

 “Give me the first success”

Example
```js
const p1 = Promise.reject("Error 1");
const p2 = Promise.resolve("Success");
const p3 = Promise.resolve("Another");

Promise.any([p1, p2, p3])
  .then(result => {
    console.log(result); // Success
  });
```

 All Fail Case
```js
Promise.any([
  Promise.reject("A"),
  Promise.reject("B")
]).catch(err => {
  console.log(err); // AggregateError
});
```
## 6. Promise.race()

Returns the first promise that settles (either success or failure)

 Think of it as:

 “Whoever finishes first wins”

 Example

```js
const p1 = new Promise(res => setTimeout(() => res("First"), 100));
const p2 = new Promise(res => setTimeout(() => res("Second"), 200));

Promise.race([p1, p2])
  .then(result => {
    console.log(result); // First
  });
```
 Failure Case
```js
const p1 = new Promise((_, rej) => setTimeout(() => rej("Error"), 100));
const p2 = new Promise(res => setTimeout(() => res("Success"), 200));

Promise.race([p1, p2])
  .catch(err => {
    console.log(err); // Error
  });
```
## Summary

Promise.resolve always resolves successfully and returns a single value; it never fails.

Promise.reject always fails and returns an error; it never resolves.

Promise.all resolves only when all promises succeed, but fails immediately if any one promise fails, returning an array of results.

Promise.allSettled always completes regardless of success or failure and returns an array describing each result.

Promise.any resolves as soon as the first promise succeeds, but fails only if all promises fail, returning a single value.

Promise.race settles as soon as the first promise finishes, whether it succeeds or fails, returning a single value or error.