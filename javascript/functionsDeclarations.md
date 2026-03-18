#  Different ways of declaring a function

```markdown
# Different Ways of Declaring a Function

Here are common ways to write functions.

## 1. Function Declaration

```js
function greet(name) {
  return "Hello " + name;
}
```
## 2. Function expression

```js
let add = function(x,y) {
  return  x+y;
};
```

## 3. Arrow Functions

```js
let add = (x,y) => x+y;
```

## 4. Constructor function

```js
let say = new Function("name", "return 'Hi ' + name;");
```

## Summary

- Functions can be written in many forms. All do the same work but look different.
