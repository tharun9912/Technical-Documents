# Popular JavaScript Array Utility Methods

- There are many popular array methods, they are 
---

## Basics

### 1. Array.push()
Adds one or more elements to the **end** of an array.
- **Mutable**
```js
let arr = [1, 2];
arr.push(3);
console.log(arr); // [1, 2, 3]
```

### 2. Array.pop()
Removes the **last element** from an array.
- **Mutable**
```js
let arr = [1, 2, 3];
let last = arr.pop();
console.log(last); // 3
console.log(arr);  // [1, 2]
```

### 3. Array.concat()
Combines two or more arrays.
- **Immutable**
```js
let arr1 = [1, 2];
let arr2 = [3, 4];
let combined = arr1.concat(arr2);
console.log(combined); // [1, 2, 3, 4]
```

### 4. Array.slice()
Returns a **part of the array**.
- **Immutable**
```js
let arr = [1, 2, 3, 4];
let part = arr.slice(1, 3);
console.log(part); // [2, 3]
```

### 5. Array.splice()
Changes array by **removing or adding elements**.
- **Mutable**
```js
let arr = [1, 2, 3, 4];
arr.splice(1, 2, 8, 9);
console.log(arr); // [1, 8, 9, 4]
```

### 6. Array.join()
Joins array elements into a **string**.
- **Immutable**
```js
let arr = ['a','b','c'];
console.log(arr.join('-')); // 'a-b-c'
```

### 7. Array.flat()
Flattens **nested arrays**.
- **Immutable**
```js
let arr = [1, [2, 3], [4]];
console.log(arr.flat()); // [1, 2, 3, 4]
```

---

## Finding

### 1. Array.find()
Returns the **first element** that satisfies a condition.
- **Immutable**
```js
let arr = [1,2,3,4];
let found = arr.find(x => x > 1);
console.log(found); // 2
```

### 2. Array.findIndex()
Returns the **index** of first element that satisfies a condition.
- **Immutable**
```js
let arr = [1,2,3,4];
console.log(arr.findIndex(x => x > 2)); // 2
```

### 3. Array.indexOf()
Returns **index** of a specific element.
- **Immutable**
```js
let arr = [1,2,3];
console.log(arr.indexOf(2)); // 1
```

### 4. Array.includes()
Checks if an element exists.
- **Immutable**
```js
let arr = [1,2,3];
console.log(arr.includes(2)); // true
```

---

## Higher Order Functions

### 1. Array.forEach()
Runs a function for **each element**.
- **Immutable** (does not return a new array)
```js
let arr = [1,2,3];
arr.forEach(x => console.log(x*2));
```

### 2. Array.filter()
Creates a **new array** with elements that pass a test.
- **Immutable**
```js
let arr = [1,2,3,4];
let evens = arr.filter(x => x % 2 === 0);
console.log(evens); // [2, 4]
```

### 3. Array.map()
Creates a **new array** by applying a function.
- **Immutable**
```js
let arr = [1,2,3];
let doubled = arr.map(x => x*2);
console.log(doubled); // [2, 4, 6]
```

### 4. Array.reduce()
Reduces array to a **single value**.
- **Immutable**
```js
let arr = [1,2,3];
let sum = arr.reduce((acc, val) => acc + val, 0);
console.log(sum); // 6
```

### 5. Array.sort()
Sorts array elements.
- **Mutable**
```js
let arr = [3,1,2];
arr.sort();
console.log(arr); // [1,2,3]
```

---

## Advanced: Method Chaining

You can chain array methods together.
```js
let arr = [1,2,3,4,5];
let result = arr
  .filter(x => x % 2 === 0)
  .map(x => x*2)
  .reduce((acc, val) => acc + val, 0);
console.log(result); // 12
```
Explanation:
- Filter even numbers `[2,4]`
- Double them `[4,8]`
- Sum `12`

---


