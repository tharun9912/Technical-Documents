# Mutable and Immutable Methods in JavaScript

## What Are Mutable and Immutable Methods?

- **Mutable methods**: These methods **change the original data** (array, object, etc.)
- **Immutable methods**: These methods **do not change the original data** and return a new copy or result

- Understanding which method is mutable or immutable helps prevent **unexpected bugs**.

---

## Arrays

### Mutable Array Methods (change original array)

| Method | Example |
|--------|---------|
| push | `arr.push(4)` adds element at end |
| pop | `arr.pop()` removes last element |
| splice | `arr.splice(1,2,'a')` removes/replace elements |
| sort | `arr.sort()` sorts array in place |
| reverse | `arr.reverse()` reverses array |

**Example:**
```js
let arr = [1,2,3];
arr.push(4);
console.log(arr); // [1,2,3,4]
```

### Immutable Array Methods (do not change original)

| Method | Example |
|--------|---------|
| concat | `arr.concat([4,5])` |
| slice | `arr.slice(1,3)` |
| map | `arr.map(x => x*2)` |
| filter | `arr.filter(x => x>1)` |
| reduce | `arr.reduce((acc, val)=> acc+val,0)` |
| flat | `arr.flat()` |

**Example:**
```js
let arr = [1,2,3];
let newArr = arr.map(x => x*2);
console.log(newArr); // [2,4,6]
console.log(arr);    // [1,2,3]
```

---

## Strings

> Strings are **always immutable** in JavaScript

| Method | Example |
|--------|---------|
| toUpperCase | `'hello'.toUpperCase()` -> 'HELLO' |
| toLowerCase | `'HELLO'.toLowerCase()` -> 'hello' |
| trim | `' hi '.trim()` -> 'hi' |
| slice | `'hello'.slice(1,4)` -> 'ell' |
| replace | `'hello'.replace('e','a')` -> 'hallo' |

**Example:**
```js
let str = 'hello';
let upper = str.toUpperCase();
console.log(upper); // 'HELLO'
console.log(str);   // 'hello'
```

---

## Objects

### Mutable Object Methods
| Method | Example |
|--------|---------|
| Object.assign | modifies target object |
| obj[key] = value | adds or changes property |
| delete obj[key] | removes property |

**Example:**
```js
let obj = {a:1};
obj.b = 2;
console.log(obj); // {a:1, b:2}
```

### Immutable Object Methods
| Method | Example |
|--------|---------|
| Object.keys | returns array of keys |
| Object.values | returns array of values |
| Object.entries | returns array of key-value pairs |
| Object.fromEntries | create new object from array |

**Example:**
```js
let obj = {a:1, b:2};
let keys = Object.keys(obj);
console.log(keys); // ['a','b']
console.log(obj);  // {a:1, b:2}
```

---

## Summary

- **Mutable**: changes original data, use carefully
- **Immutable**: creates new data, original remains safe
