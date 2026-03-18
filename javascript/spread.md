# Spread Operator in JavaScript 

  - The spread operator (...) is used to:
       -  expand (spread) elements of arrays or objects

  - It makes your code: cleaner,shorter and easier to read. 


-   It looks simple, but it’s very powerful.

## Spread with Arrays

   Copy an Array
   ```js
   let arr1 = [1, 2, 3];
   let arr2 = [...arr1];
   console.log(arr2);
   ```

Output: [1, 2, 3]

  Creates a copy, not reference

  Merge Arrays

```js
   let a = [1, 2];
   let b = [3, 4];
   let result = [...a, ...b];
   console.log(result);
```

 Output: [1, 2, 3, 4]

- Add Elements

```js
   let arr = [2, 3];
   let newArr = [1, ...arr, 4];
   console.log(newArr);
```
 Output: [1, 2, 3, 4]

##  Spread with Objects

-  Copy Object

```js
  let user = { name: "John", age: 25 };
  let copy = { ...user };
  console.log(copy);
```
-  Merge Objects
```js
   let obj1 = { a: 1 };
   let obj2 = { b: 2 };
   let result = { ...obj1, ...obj2 };
    console.log(result);
```

Output: { a: 1, b: 2 }

-  Override Values
```js
let user = { name: "John", age: 25 };

let updated = { ...user, age: 30 };

console.log(updated);
```

  Output: { name: "John", age: 30 }

## Spread in Function Calls

```js
  let numbers = [1, 2, 3];
   function sum(a, b, c) {
     return a + b + c;
    }
   console.log(sum(...numbers));
```
 Output: 6

-  It spreads array into arguments


##  When to Use Spread

 Use it when:
    
    - Copying arrays/objects
     
    - Merging data

    - Updating state

    - Passing arguments

## Summary

 - spread operator spreads elements.
 
 - Works with arrays, objects, functions

 - Makes code clean and short

 - Creates shallow copy

 - Very useful in modern JavaScript