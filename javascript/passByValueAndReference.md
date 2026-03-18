# Pass by reference and pass by value 

- When we write functions, we often pass data (like numbers or objects) into them. But how this data is passed affects whether the original data can be changed inside the function.

- Two ways to pass data to functions ,they are

## Pass by value

- When a value is passed by value, the function gets a copy of the original data.

```js
  function changeNumber(num) {
     num = 100; // changes only the local copy  
  }

let original = 50;
changeNumber(original);

console.log(original); // still 50
```

### When does this happen?

- Primitive types like numbers, strings, booleans are passed by value

- The function cannot change the original because it only works with a copy.


## Pass by reference

- When data is passed by reference, the function can access the original data.
 
- This means changes inside the function can affect the original variable.

```js
   function updateObject(obj) {
  obj.value = 100; // changes the original object
}

let data = { value: 10 };
updateObject(data);

console.log(data.value); // now 100
```

### When does this happen?

- Objects, arrays, lists, and other non‑primitive data types are passed by reference.

- The function gets a reference (pointer) to the original data.

- Changes inside the function affect the original variable.


## Summary

- Pass by value passes the copy of the data

- Pass by reference passes the references of value, can modify the original.