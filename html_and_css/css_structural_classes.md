# CSS Structural Classes

- Structural CSS classes are classes that help organize the layout and structure of a webpage.

- They are used to control how elements are arranged on the page.

- We use them to organize page layout, create sections, align content and control spacing.

- Structural css classes address problems such as code duplication, inconsistent patterns and increase maintenance.

## Key concepts

**Utility classes**

- A utility class is a single purpose CSS class that applies a specific styling rule.

Example : 
```html
.text-center {
    text-align: center;
}
```

**Structural classes**

- Structural classes focus on layout and positioning elements.

- It tells how elements are structured within a layout.

- Major categories include

**Display Utilities**

- Control how elements are rendered.

- **Examples**
  
  display:block ,  display:inline , display:inline-block  etc.

  ```css
  .d-flex {
    display: flex;
    }
  ```

**Flexbox utilities**

- flex-direction:row, justify-content:center, align-items:Center.

```css
.justify-center {
    justify-content: center;
}
```

**Grid utilities**

- Grid utilities help structure complex layouts with predictable rules

```css
.grid {
    display: grid;
}
```

**Spacing utilities**

- Margin,padding are some spacing utilities.

```css
.mt-1 {
    margin-top: 0.25rem;
}
```

**Overflow utilities**

- Control element overflow behavior.

- overflow:auto, overflow:hidden,overflow-x:scroll are some of overflow utilities.

## Conclusion

- CSS structural classes provide a powerful foundation for modern layout development.

- By abstracting common patterns into reusable utilities, they reduce redundancy, enhance maintainability, and promote predictable UI structures.