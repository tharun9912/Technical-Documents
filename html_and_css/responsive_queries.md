# CSS Responsive Queries

## What are media queries?

- They help a website adjust to different screen sizes.

- They make websites responsive (work on mobile, tablet, desktop)

- They apply CSS only when a condition is true.

- Media Queries are a feature of CSS3.

### Basic Syntax

```css
@media (condition) {
   /* CSS code */
}
```

**Example**
```css
@media (max-width: 480px) {
   body {
      background-color: lightblue;
   }
}
```
## Common conditions used 

- max-width → For smaller screens

- min-width → For larger screens

- orientation → Portrait or Landscape

- min-resolution → For high-quality screens

## What is a breakpoint?

- A breakpoint is where layout changes.

- Mobile : 0 - 480px
           
  Tablet : 481px - 1024px

  Desktop : 1025+.

## Mobile first approach

- First write CSS for mobile.

- Then use min-width for bigger screens.

```css
/* Default for mobile */
.container {
   display: block;
}

/* For tablet and larger */
@media (min-width: 768px) {
   .container {
      display: flex;
   }
}
```

## Why media queries are important?

- Makes website responsive
 
- Works on all devices.

- No need for separate mobile website.

## Conclusion

- Media Queries help change layout based on screen size.

- They are key for responsive web design.

- They are very important for modern frontend development.

## References

- https://www.w3schools.com/css/css3_mediaqueries.asp