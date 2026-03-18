# JavaScript Data Types

## Primitive Data Types

- Primitive data types store single values and are immutable (cannot be changed directly).

- There are 7 primitive data types in JavaScript.

### 1.Number

- The Number data type represents both integers and decimal numbers.

```javascript
let age = 45;
let price = 100.99;
let temperature = -4;
```
- Special numeric values

```javascript
  Infinity
  -Infinity
  NaN   // Not a Number
```

### 2. string

- A String represents text or characters.

- Strings can be written using  single quotes,double quotes and backticks.

```javascript
let name = "Tharun";
let city = 'Bangalore';
let message = `hey ${name}`;
```
### 3. Boolean 

- Boolean represents true or false values.

- It is mainly used in conditions and logical operations.

```javascript
let isWorking=true;
let isDeployed=false;
```

### 4. Null

- null represents absence of a value.

- It means the variable exists but currently has no value.

### 5. Undefined

- A variable that is declared but not assigned any value has the type undefined.

```javascript
let name;
console.log(name);
```
- prints undefined.

### Bigint

- BigInt is used to represent very large integers beyond the limit of the Number type.

```javascript
let bigNumber = 123456789012345678901234567890344n;
```

- The n at the end indicates BigInt.

## Non-Primitive data types

- Non-primitive data types store collections of values.

- Object,Array,Function.

### Object

- An object stores data in key-value pairs.

```javascript
    let person = {
    name: "Tharun",
    age: 23,
    city: "Bangalore"
   };
```
### Array

- An array stores multiple values in a single variable.

```javascript
let numbers = [1, 2, 3, 4];
let fruits = ["virat","rohit","dhoni"];
```

### Function

-  A function is a reusable block of code.
  
```javascript
function greet(name){
    return "Hello" + name;
}

console.log(greet("Tharun"));
```
- Above example prints Hello tharun.

## Conclusion

- JavaScript provides multiple data types to handle different kinds of data.

- Divided into primitive and non-primitive data types.


