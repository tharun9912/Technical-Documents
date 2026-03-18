#  Template Literals in JavaScript

Template literals are a modern way to work with strings in JavaScript.
 
They help you:
- Add variables inside strings  
- Write multi-line text  
- Create dynamic strings easily  

- Use backticks instead of quotes:


```js
  let name = "tharun";

  let message = `Hello ${name}`;
 
  console.log(message); // hello tharun
```

## Why Template Literals?

 - Old way:
    
 ```js
      let name = "John";
      let msg = "Hello " + name;
 ```

Hard to read when complex.
  
- New way:

  ```js
   let msg = `Hello ${name}`;
  ```
     Cleaner and easier

## Multi-line Strings

```js
let text = `Hello
 tharun,
  good morning`;

console.log(text);
```

## Expressions inside strings

```js
 let age = 23;

console.log(`You are ${age >= 18 ? "Adult" : "Minor"}`);
```
##  When to Use Template Literals

Use them when:
  - Creating dynamic strings
  - Printing variables
  - Writing multi-line text
  - Building UI strings

## Summary

  - Use backticks `

  - ${} for variables and expressions

  - Supports multi-line strings

  - Cleaner than string concatenation