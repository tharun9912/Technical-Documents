# AMA-4

## 1. GET vs POST

### GET
- Used to **get data** from server
- Data is sent in URL

Example:
GET /users?id=10

### POST
- Used to **send data** to server
- Data is sent in body (not visible in URL)

Example:
POST /users

## 2. how to get first child in DOM?
 
 - Using firstChild property.

### Example

```html
<div id="box">
  <p>Hello</p>
</div>
```

```js
const box = document.getElementById("box");
console.log(box.firstChild);
```

## 3. Why .catch at the end?

- `.catch()` is used to **handle errors in promises**

### Example
```js
fetch("wrong-url")
  .then(res => res.json())
  .catch(err => console.log("Error occurred"));
```
### Why at end?
- It catches errors from all `.then()` above it

---

## 4. Event Loop

### Simple Idea
- JavaScript runs **one task at a time**
- Event loop manages async tasks

### Example
console.log("Start");

setTimeout(() => {
  console.log("Timeout");
}, 0);

console.log("End");

### Output
Start  
End  
Timeout  

### Why?
- Async code goes to queue
- Event loop executes it later

---

## 5. Promise APIs

### Promise.all()
- Runs multiple promises
- Fails if one fails

### Promise.allSettled()
- Waits for all (success + fail)

### Promise.race()
- Returns first finished promise

### Promise.any()
- Returns first successful promise


## 6. seal vs freeze

### Object.seal()
- Cannot add/remove properties
- Can modify values

### Object.freeze()
- Cannot add/remove/modify anything

### Example

```js
const obj = { a: 1 };
Object.freeze(obj);
obj.a = 2; // not allowed
```


## 7. 404 in HTTP

- Means **Page Not Found**

### Example

You open a wrong URL:

Server returns 404

---

## 8. textContent vs innerText

### textContent
- Gets all text (including hidden text)

### innerText
- Gets only visible text

---

## 9. innerHTML vs innerText

### innerHTML
- Reads HTML tags also

Example:
```html
div.innerHTML = "<b>Hello</b>";
```
### innerText
- reads Only text

Example:

```html
div.innerText = "Hello";
```

## 10. onclick vs addEventListener

### onclick
- Can assign only one function

Example:

```js
btn.onclick = () => alert("Hello");
```

### addEventListener
- Can add multiple event handlers

Example:
```js
btn.addEventListener("click", () => alert("Hello"));
```
### Difference
- onclick → simple, one handler  
- addEventListener → flexible, multiple handlers  


