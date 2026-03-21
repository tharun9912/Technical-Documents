# Web Browser APIs 

## What are Web Browser APIs?

Web Browser APIs are built-in features provided by the browser (like Chrome, Firefox) that allow JavaScript to interact with the browser and the user's device.

They help you do things like:
- Fetch data from servers
- Manipulate web pages
- Store data in the browser
- Access device features.

---

## Why are Browser APIs Important?

Without Browser APIs, JavaScript can only do calculations and basic logic.

With APIs, JavaScript can:
- Update the UI dynamically
- Make web apps interactive
- Communicate with backend servers

---

## Common Types of Browser APIs

### 1. DOM API (Document Object Model)

Used to manipulate HTML and CSS.

Example:
```javascript
document.getElementById("title").innerHTML = "Hello World";
```

### 2. Fetch API

Used to make HTTP requests (get data from server).

Example:

```js
fetch("https://api.example.com/data")
  .then(res => res.json())
  .then(data => console.log(data));
```
### 3. Local Storage API

Used to store data in the browser.

Example:

```js
localStorage.setItem("name", "Tharun");
console.log(localStorage.getItem("name"));
```
### 4. Geolocation API

Used to get user's location.

Example:
```js
navigator.geolocation.getCurrentPosition((position) => {
  console.log(position.coords.latitude);
});
```
### 5. Timer APIs

Used to run code after some time.

Example:
```js
setTimeout(() => {
  console.log("Hello after 2 seconds");
}, 2000);
```

## Summary

 - API	Purpose
 - DOM API	Modify web pages
 - Fetch API	Get data from server
 - Local Storage	Store data
 - Geo location	get location
 - Timer APIs	Run delayed code