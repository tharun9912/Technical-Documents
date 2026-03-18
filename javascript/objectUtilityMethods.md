# Popular JavaScript Object Utility Methods

- Objects are mutable by default in JavaScript, but some methods return a new object.

---

## Basics

### 1. Object.keys()
Returns an array of object keys.
- **Immutable**
```js
let obj = {a:1, b:2};
console.log(Object.keys(obj)); // ['a','b']
```

### 2. Object.values()
Returns an array of object values.
- **Immutable**
```js
let obj = {a:1, b:2};
console.log(Object.values(obj)); // [1,2]
```

### 3. Object.entries()
Returns array of [key, value] pairs.
- **Immutable**
```js
let obj = {a:1, b:2};
console.log(Object.entries(obj)); // [['a',1], ['b',2]]
```

### 4. Object.assign()
Copies properties from one or more objects to a target object.
- **Mutable** (changes target)
```js
let target = {a:1};
let source = {b:2};
Object.assign(target, source);
console.log(target); // {a:1, b:2}
```

### 5. Object.hasOwnProperty()
Checks if object has specific property.
- **Immutable**
```js
let obj = {a:1};
console.log(obj.hasOwnProperty('a')); // true
console.log(obj.hasOwnProperty('b')); // false
```

### 6. Object.freeze()
Freezes object to **prevent changes**.
- **Mutable (prevents mutation)**
```js
let obj = {a:1};
Object.freeze(obj);
obj.a = 2;
console.log(obj.a); // 1
```

### 7. Object.seal()
Prevents adding/deleting properties but **allows modification**.
- **Mutable (restricted)**
```js
let obj = {a:1};
Object.seal(obj);
obj.a = 2; // allowed
obj.b = 3; // ignored
console.log(obj); // {a:2}
```

### 8. Object.fromEntries()
Converts array of key-value pairs into object.
- **Immutable**
```js
let entries = [['a',1],['b',2]];
let obj = Object.fromEntries(entries);
console.log(obj); // {a:1, b:2}
```

### 9. Object.getOwnPropertyNames()
Returns all property names (including non-enumerable).
- **Immutable**
```js
let obj = {a:1, b:2};
console.log(Object.getOwnPropertyNames(obj)); // ['a','b']
```

### 10. Object.getOwnPropertyDescriptors()
Returns descriptors for all properties.
- **Immutable**
```js
let obj = {a:1};
console.log(Object.getOwnPropertyDescriptors(obj));
/*
{
  a: {
    value: 1,
    writable: true,
    enumerable: true,
    configurable: true
  }
}
*/
```

---

## Summary 

-  Objects are mutable in JavaScript, but you can use `freeze` or `seal` to control modifications.
