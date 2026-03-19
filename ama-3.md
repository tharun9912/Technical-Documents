# JavaScript Interview Notes (Simple)

## 1. Is JavaScript Sync or Async?

JavaScript is synchronous by default but can do async tasks.

Example:

``` js
console.log("1");
setTimeout(() => console.log("2"), 1000);
console.log("3");
```

Output: 1 3 2



## 2. value === undefined vs !value

``` js
let value = 0;

if (!value) console.log("false"); // wrong
if (value === undefined) console.log("undefined"); // correct
```

!value checks many falsy values like 0, "", null. === undefined checks
only undefined.


## 3. Ways to declare function

- Using function keyword.

- Function expression.

- Arrow function.

``` js
function add(a, b) { return a + b; }

const add2 = function(a, b) { return a + b; }

const add3 = (a, b) => a + b;
```


## 4. Callback function

- A function that is passed as an argument to another function and is executed later.

``` js
function user(name, callback) {
  console.log("Hi " + name);
  callback();
}

function location() {
  console.log("From bengaluru");
}

user("Tharun", location);
```
-output   

Hi Tharun
From bengaluru




## 5. setTimeout

- setTimeout is used to run a function after a specific time.

``` js
setTimeout(() => {
  console.log("hello world after 3 sec");
}, 3000);
```


## 6. Object

- An object in javascript is a collection of key value pairs.It is used to store related data and functions together.

``` js
const user = {
  name: "Tharun",
  age: 23
};
```


## 7. What happens if function not invoked after declaration?

- If function declared but didn't invoke , it won't give any error.
- But it is a bad practice.

## 8. Function Declaration vs Expression

Declaration 
    - supports hoisting
    - Can use this keyword.
Expression 
    - Does not support hoisting
    - We cannot use this keyword with function expression.


## 9. Are Strings  methods mutable?

No, strings methods are immutable.


## 10.  Explain trim() method in javascript?

- trim method is used to remove empty spaces on the starting and ending of a string.

``` js
let str = "  hello  ";
console.log(str.trim());
```
output: hello

## 11. Object methods

- popular object methods :
``` js
Object.keys(obj);
Object.values(obj);
Object.entries(obj);
```


## 12. What are the states  in a promise?

-   Pending
-   Fulfilled
-   Rejected


## 13. what happens if we subtract  Number from String number?


``` js
console.log(5 - "2"); // 3
console.log(5 - "abc"); // NaN
```

------------------------------------------------------------------------

## 14. Event Delegation

- Event delegation is a technique where you add a single event listener to a parent element instead of adding listeners to multiple child elements. 

``` js
parent.addEventListener("click", (e) => {
  if (e.target.tagName === "BUTTON") {
    console.log("Clicked");
  }
});
```


## 15. How to get key and value pairs from object? 

- entries method helps to get key and value pairs of an object.
``` js
Object.entries({a:1, b:2});  // [a,1] [b,2]
```


## 16. Mention popular array methods.

-  push 
    - push used to add elements to an array.
- pop
   - pop is used to delete elements in an array.
- filter
  - filter method returns a new array containing elements that satisfy a given condition.


Example:

``` js
[1,2,3].map(n => n * 2); // 2,4,6
[1,2,3].filter((ele)=> ele%2==0) // 2
 ```