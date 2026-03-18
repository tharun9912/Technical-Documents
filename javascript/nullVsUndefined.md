# Difference Between null and undefined in JavaScript 

In JavaScript, `null` and `undefined` both represent **empty values**, but they are different.

---

## What is `undefined`?

`undefined` means:  A variable is declared but **no value is assigned**

---

### Example:

```js
let x;
console.log(x);
```

Output:
undefined

 JavaScript automatically assigns undefined

```js
function test(a) {
  console.log(a);
}

test();
```
 Output:  undefined

 Parameter not passed → undefined

## What is null?

 null means:

    - Intentional absence of value

    - It is set by the developer

Example:
```js
let user = null;
console.log(user);
```
Output: null


## Equality Comparison
```js
console.log(null == undefined);
console.log(null === undefined);
```
Output: true false

Explanation:

== → considers them equal

=== → different types → false



##  When to Use What

Use undefined when:

   - Value is not assigned

   -  Function parameter missing

   - Property does not exist

Use null when:

   - You want to clear a value

  - You intentionally set empty value

Reset variables

##  Summary

undefined → not assigned

null → intentionally empty

== treats them same

=== treats them different
