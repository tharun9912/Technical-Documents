# Popular JavaScript String Utility Methods

-  In JavaScript, **strings are immutable**, so  methods return a new string.

---

## Basics

### 1. String.length
Returns the number of characters.
- **Immutable**
```js
let str = 'Hello';
console.log(str.length); // 5
```

### 2. String.toUpperCase()
Converts all letters to uppercase.
- **Immutable**
```js
let str = 'hello';
let upper = str.toUpperCase();
console.log(upper); // 'HELLO'
console.log(str);   // 'hello'
```

### 3. String.toLowerCase()
Converts all letters to lowercase.
- **Immutable**
```js
let str = 'HELLO';
console.log(str.toLowerCase()); // 'hello'
```

### 4. String.trim()
Removes whitespace from both ends.
- **Immutable**
```js
let str = '   hi   ';
console.log(str.trim()); // 'hi'
```

### 5. String.concat()
Concatenates strings.
- **Immutable**
```js
let str1 = 'Hello';
let str2 = 'World';
let result = str1.concat(' ', str2);
console.log(result); // 'Hello World'
```

### 6. String.slice()
Returns a part of string.
- **Immutable**
```js
let str = 'Hello';
console.log(str.slice(1,4)); // 'ell'
```

### 7. String.substring()
Similar to slice.
- **Immutable**
```js
let str = 'Hello';
console.log(str.substring(1,4)); // 'ell'
```

### 8. String.charAt()
Returns character at index.
- **Immutable**
```js
let str = 'Hello';
console.log(str.charAt(1)); // 'e'
```

### 9. String.split()
Splits string into an array.
- **Immutable**
```js
let str = 'a,b,c';
let arr = str.split(',');
console.log(arr); // ['a','b','c']
```

### 10. String.includes()
Checks if string contains substring.
- **Immutable**
```js
let str = 'Hello World';
console.log(str.includes('World')); // true
```

### 11. String.indexOf()
Finds index of substring.
- **Immutable**
```js
let str = 'Hello World';
console.log(str.indexOf('World')); // 6
```

### 12. String.replace()
Replaces part of string.
- **Immutable**
```js
let str = 'Hello World';
let newStr = str.replace('World', 'JS');
console.log(newStr); // 'Hello JS'
```

### 13. String.repeat()
Repeats string multiple times.
- **Immutable**
```js
let str = 'Hello ';
console.log(str.repeat(3)); // 'Hello Hello Hello '
```

### 14. String.startsWith()
Checks if string starts with substring.
- **Immutable**
```js
let str = 'Hello';
console.log(str.startsWith('He')); // true
```

### 15. String.endsWith()
Checks if string ends with substring.
- **Immutable**
```js
let str = 'Hello';
console.log(str.endsWith('lo')); // true
```

### 16. String.toString()
Converts value to string.
- **Immutable**
```js
let num = 123;
console.log(num.toString()); // '123'
```

### 17. String.padStart() / String.padEnd()
Pads string to a certain length.
- **Immutable**
```js
let str = '5';
console.log(str.padStart(3, '0')); // '005'
console.log(str.padEnd(3, '0'));   // '500'
```

### 18. String.repeat()
Repeats string N times.
- **Immutable**
```js
let str = 'ha';
console.log(str.repeat(3)); // 'hahaha'
```

---

## Summary 

- Strings in JavaScript are **immutable**. Methods that look like they change the string actually **return a new string**.
