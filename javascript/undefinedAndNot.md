# value === undefined vs !value in JavaScript 

 - In JavaScript, we often check if a value exists.

 - Two common ways:

   - value === undefined

   - !value

 They may look similar, but they are very different.

##  What is !value?

 - !value means: “value is falsy”

  - Falsy values in JavaScript: 
      - false
      - 0
      - "" (empty string)
      - null
      - undefined
      - NaN

Example:
```js
let value = 0;

if (!value) {
  console.log("Value is falsy");
}
```
Output:

Value is falsy

   - 0 is a valid value, but treated as false ❌

## What is value === undefined?

-  It checks only one thing:
- Is the value exactly undefined?

Example:

```js
let value;

if (value === undefined) {
  console.log("Value is undefined");
}
```

 Output:

   Value is undefined

 Only checks for missing value

## Key Difference

Check	What it means

 - !value	Value is falsy (many cases)
  - value === undefined	Value is specifically undefined


##  Correct Way Using === undefined

```js
let price = 0;

if (price === undefined) {
  console.log("Price not set");
}
```
 Output:

(no output)


##  When to Use What

 ### Use value === undefined when:

   You want to check missing value only

   Avoid bugs

   Working with APIs or optional fields

### Use !value when:

   You want to check any falsy value


## Summary

!value checks many values (risky)

value === undefined checks only undefined (safe)

Use strict checks for better control

Avoid bugs by being specific