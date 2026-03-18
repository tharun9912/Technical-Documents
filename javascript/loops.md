# Loops

- Loops are used to repeat code multiple times without writing it again and again. 

- JavaScript provides several types of loops for different situations.

## for loop with numbers

- The `for` loop runs a block of code a fixed number of times.


```js
   for (let i = 0; i < 5; i++) {
      console.log(i);
    }
```

## 2. For...in Loop 

- The for...in loop is used to iterate over object keys.

```js
  let person = { name: "tharun", age: 23 };
  for (let key in person) {
    console.log(key, person[key]);  // prints name, tharun and age,23.
  }
```

## 3. For...of Loop 

- The for...of loop is used to iterate over arrays or other iterable objects.

```js
  let names = ["tharun", "varun", "kiran"];
  for (let name of names) {
    console.log(name);  // logs the names in array.
  }
```

## 4. forEach 

- The forEach method executes a function for each element in an array.

```js
  let numbers = [1, 2, 3];
numbers.forEach(function(num) {
  console.log(num);
});
```

- Can also use for arrow functions.

```js
  numbers.forEach(num => console.log(num));
```

## 5. while loop

- The while loop runs as long as the condition is true.

```js
  let i = 0;
  while (i < 5) {
     console.log(i);
     i++;             // runs while i less than 5.
   }
```

## 6. do while loop

- The do...while loop runs at least once before checking the condition.

```js
let i = 0;
do {
  console.log(i);
  i++;
} while (i < 5);
```

- do while loop executes the code once even if the condition is false.

## Summary

- for loop executes for fixed number of times.

- while loop executes until condition is true.

- for...in loop used in objects.

- for...of loop used in arrays and objects.



