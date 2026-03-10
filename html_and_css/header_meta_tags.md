# Common Header Tags

## Meta tags in header

- Meta tags are placed inside the <head> section of an HTML document.

- They provide information about the webpage.

- Meta tags do not display content on the page.

- They help browsers, search engines, and social media understand the page.

- It is written using the <meta> element.

- Ity usually contains attributes like :

  - charset 
  - name
  - content

```css
<head>
  <meta charset="UTF-8">
</head>
```

## Common Header Meta tags

**Character encoding**

- Defines the character encoding for the webpage.

- Prevents text display errors.


```css
<meta charset="UTF-8">
```

**Viewport**

- Makes the website responsive.

- Controls how the page looks on mobile devices.
 
- width=device-width → sets width to device width.

- initial-scale=1.0 → sets default zoom level.

**Page Description**

- Gives a short summary of the webpage.

- Used by search engines such as google.

```css
<meta name="description" content="This is a tutorial website for learning HTML and CSS.">
```

**Keywords**

- Lists important keywords of the page.

```css
<meta name="keywords" content="HTML, CSS, Web Development">
```
  
**Refresh/Redirect**

- Refresh the page for every specified time.

```css
<meta http-equiv="refresh" content="5">
```
- Refreshes page after 5 seconds.

**Author**

```css
<meta name="author" content="Tharun">
```
- Specifies the author of the webpage.

## Conclusion

- Meta tags are small but very important.

- They help browsers and search engines understand your website.

- Always include charset, viewport and description.

## References

- https://www.geeksforgeeks.org/html/html-meta-tag/