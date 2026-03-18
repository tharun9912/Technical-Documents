# When to Use forEach vs Array Utility Methods (map, filter, reduce)

## 1. Array.forEach()
- Use when you want to **perform side effects** (like printing, updating external variables, or logging)
- Does **not return a new array**
- Iterates over each element in an array

### Example
```js
let numbers = [1, 2, 3];
numbers.forEach(num => console.log(num * 3));
// Output: 3, 6, 9
```
- Use `forEach` when you just need to **do something with each element** but don't need a new array.

---

## 2. Array.map()
- Use when you want to **create a new array** by transforming each element
- Returns a **new array** with the modified values
- Does **not change original array** (immutable)

### Example
```js
let numbers = [1, 2, 3];
let doubled = numbers.map(num => num * 2);
console.log(doubled); // [2, 4, 6]
console.log(numbers); // [1, 2, 3]
```
-  Use `map` when you want a **new transformed array**.

---

## 3. Array.filter()
- Use when you want a **subset of elements** that satisfy a condition
- Returns a **new array** with only the elements that pass the test
- Original array is **unchanged** (immutable)

### Example
```js
let numbers = [1, 2, 3, 4, 5];
let evens = numbers.filter(num => num % 2 === 0);
console.log(evens); // [2, 4]
```
- Use `filter` when you want to **pick certain elements** from an array.

---

## 4. Array.reduce()
- Use when you want to **combine elements into a single value**
- Examples: sum, product, maximum, concatenation
- Returns a **single value**

### Example
```js
let numbers = [1, 2, 3, 4];
let sum = numbers.reduce((acc, num) => acc + num, 0);
console.log(sum); // 10
```
- Use `reduce` when you want to **accumulate or compute a single result** from an array.

---


## Example Combining Methods
```js
let numbers = [1, 2, 3, 4, 5];

// Filter even numbers, double them, and sum
let result = numbers
  .filter(num => num % 2 === 0) // [2, 4]
  .map(num => num * 2)           // [4, 8]
  .reduce((acc, val) => acc + val, 0); // 12

console.log(result); // 12
```

**Summary:**
- **forEach**: do something with each element (no new array)
- **map**: transform each element (new array)
- **filter**: select elements (new array)
- **reduce**: combine elements (single value)
