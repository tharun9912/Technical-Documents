# Inline vs Block Elements.

- Inline and block level elements are two types of elements in html.

## Block Elements

- It starts on a new line.

- Takes full width of its parent container.

- Can have height and weight.

- Allows margin and padding.

**Common block level elements**

 - ```<div>,<section>,<article>,<header>``` are common examples.

```bash
<p>paragraph 1</p>
<p>paragraph 2</p>
``` 
- Here each paragraph starts on new line and takes full width.

## Inline Elements

- Takes only the required width

- Does not fully allow width and height

- Does not start on a new line

**Common inline elements**

- ```<span>, <a> , <strong> , <label>``` 

```
<p>This is <span>inline</span> text.</p>
```
- Here the word "inline" stays in the same line.

- It does not break the line.


## Inline-block elements

- Inline-block elements has both features, stays inline and accepts width and height.

``` 
  span
  {
    display:inline-block;
    width:100px;
    height:100px;
  }
```
- Here width and height works and it stays inline.

## Conclusion

- Block elements start on a new line and take full width.

- Inline elements stay in the same line and take only required space.

- Inline-block combines both behaviors.

## References

- https://www.w3schools.com/html/html_blocks.asp