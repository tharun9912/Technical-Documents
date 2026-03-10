# Flex and Grid Layouts 

- Earlier, developers used floats and positioning, which were complex.

- Modern websites need flexible and responsive layouts.

- CSS introduced Flexbox and Grid to make layout design easier.

## Flexbox

### what is Flexbox?

- Flexbox is a one-dimensional layout system.

- It works either in a row or a column.

- It helps align and distribute space between items in a container.

#### Flexbox concepts

**Flex Container**

- The parent element.

- We apply display: flex; to activate flexbox.

```css
.container {
  display: flex;
}
```
**Flex Items**

- The child elements inside the flex container.

- Automatically arranged in a row (default).

**Main Axis**

- Default direction: left to right (row).

Controlled using:

```css
flex-direction: row;
flex-direction: column;
```

#### Flexbox properties

**Justify-content**

- Aligns items horizontally (main axis).

```css
justify-content: center;
justify-content: space-between;
```
**align-items**

-Aligns items vertically (cross axis).
```css
align-items: center;
```

## CSS Grid Layout

### What is CSS Grid ?

- Grid is a two-dimensional layout system.

- It works with both rows and columns at the same time.

- Best for full-page layouts.

### Grid Properties

**Grid Container**

- Apply display: grid;

```css
.container {
  display: grid;
}
```

**Grid Rows and Columns**

```css
grid-template-columns: 200px 200px 200px;
grid-template-rows: 100px 100px;
```
**Gap**

- Space between grid items.

**Grid Areas**

```css
grid-template-areas:
  "header header"
  "sidebar content"
  "footer footer";
```

## Conclusion

- Flexbox is best for one direction layouts.

- Grid is best for complex two-direction layouts.

- Both make responsive design easier.

## References

- https://www.geeksforgeeks.org/css/css-grid-property.

- https://www.geeksforgeeks.org/css/css-flex-property/