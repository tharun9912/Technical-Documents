# Scopes in JavaScript

- In JavaScript, scope refers to the area or region in a program where a variable can be accessed.

- It determines where variables and functions are visible and usable in the code.

- Types of scopes in JavaScript are global scope,function scope and block scope.

## Global Scope

- A variable declared outside any function or block is called a global variable.

- It can be accessed anywhere in the program.

```javascript
let name = "tharun";

function display(){
    console.log(city);
}

display();
console.log(city);
```
- Here city is in global scope it can be accessed inside and outside function.

## Function scope

- Variables declared inside a function are accessible only within that function.

```javascript
function greet(){
    let message = "Hello";

    console.log(message);
}

greet();
console.log(message); // Error
```

-  "message" variable is declared inside the function, cannot be accessed from outside of the function.


## Block scope

- Block scope refers to variables declared inside a block { } using let or const.

- Blocks include  if statements, loops and functions.

```javascript
if(true){
    let x = 45;
    console.log(x);
}

console.log(x); // Error
``` 

- Gives error because it can be accessed only inside the block.


## Lexical Scope

-In lexical scope, a function can access variables from its outer scope.

```javascript
function outer(){
    let name = "Tharun";

    function inner(){
        console.log(name);
    }

    inner();
}

outer();
```
- inner() can access the variable name from outer().


## Conclusion

- JavaScript supports global scope, function scope, and block scope.

- Scope help to prevents variable conflicts.