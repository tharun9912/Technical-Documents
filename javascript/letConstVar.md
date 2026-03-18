# let, const, var

- In JavaScript, var, let, and const are keywords used to declare variables.

- These three differ in scope, reassignment, and redeclaration behavior.

## var

- var is the old way of declaring variables in JavaScript .

- It was used before ES6 (2015).

- Key features are 

  - Function scoped.

  - Can be redeclared.
 
  - Can be reassigned.

  - Accessible outside blocks.

```javascript
var name = "Tharun";
var name = "virat";   // redeclaration allowed

name = "rohit";      // reassignment allowed

console.log(name);
```

## let 

- let was introduced in ES6 (ECMAScript 2015) and is used for block-scoped variables.

- Key features are block scoped, cannot be redeclared and can be reassigned.

```javascript
if(true){
    let x = 50;
    x=75;         // reassignment allowed
    console.log(x);
}
console.log(x); // Error  because it is block scoped.
```

## const

- const is also introduced in ES6 and is used for constant values.

- Key features are block scoped,cannot be redeclared and must be initialized during declaration.

```javascript
const value = 45;
console.log(value);
```

## const with objects and arrays

- object and arrays declared using const can be modified.

```javascript
const numbers = [1,2,3];

numbers.push(4); // allowed to add.
```

```javascript
const person = {
    name: "Tharun",
    age: 23
};

person.name = "varun"; // allowed
```

## Why we must not use var?

 - We should avoid using var in JavaScript because it can create bugs and confusion in code.

 - Because 

   - var does not respect block { } scope, which can cause unexpected behavior.

   ```javascript
   if(true){
    var x = 100;
    }
    console.log(x); // 100
   ```

   - x is declared inside the if block, but it is still accessible outside the block, which may cause bugs.

   - let correctly limits the variable to the block.

   - var allows declaring the same variable multiple times, which can cause mistakes.

   ```javascript
     var name = "Tharun";
     var name = "virat";
     console.log(name); // virat, first value gets overwritten silently.
   ```

   - Variables declared with var are hoisted and initialized with undefined, which can create confusing results.

    ```javascript
      console.log(a);
      var a = 10;  // undefined.this can confuse developers.
    ```

    - var can sometimes create unwanted global variables, especially inside loops or blocks.
-  Best practice
   
   - Use const for values that should not change.

   - Use let for variables that change.

## Conclusion

- var, let, and const are used to declare variables in JavaScript.

- While var was used in older JavaScript versions, modern JavaScript prefers let and const .

- Avoid var, use const and let to avoid errors . 



