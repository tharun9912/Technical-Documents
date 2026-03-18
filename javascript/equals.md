# Difference Between == and === in JavaScript 


In JavaScript, we use:

== (loose equality)

=== (strict equality)

-  Both are used to compare values, but they behave differently.

##  == (Loose Equality)

 == compares values after converting types

Example:
```js
console.log(5 == "5");
```
 Output: true

    "5" (string) is converted to number 5  . Then comparison happens
 So:
    5 == "5"  → true

## === (Strict Equality)

 === compares:Value and Type 
   
    No conversion happens

Example:
```js
console.log(5 === "5");
```
 Output: false

   - Number ≠ String ,types are different

Example 

```js
console.log("" == false);
console.log("" === false);
```
 Output: true   false

Example 
```js
console.log(null == undefined);
console.log(null === undefined);
```
 Output: true false


 JavaScript converts values automatically
 This can cause unexpected bugs

##  Best Practice 

 Always use: ===

Example:

```js
if (value === 0) {
  console.log("Value is zero");
}
```
 Safer and predictable


##  Summary

== → compares after type conversion

=== → compares without conversion

=== is safer and recommended

== can cause unexpected results.