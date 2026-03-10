# Positioning : Relative and Absolute

-  Positioning controls where an element appears on a webpage.
  
-  Position values includes static, relative, absolute, fixed and sticky.

## Default Position

-  An element with relative position remains in the normal document flow , but can change using top,right,left and bottom.

- It won't affect other elements positions.

### Key characteristics 

- Original space is reserved.

- Values in top, right, bottom, left shift the element visually without reflowing siblings.

Example :- 

```html
<div class="relative-box">Relative</div>

<style>
.relative-box {
    position: relative;
    top: 20px;
    left: 30px;
    background:red;
    padding: 10px;
}
</style>
```

## Position:Absolute

- An element with  **position:absolute** is removed from the normal flow and positioned relative to its nearest positioned ancestor.

### Key characteristics 

- Removed from document flow.

- Other elements behave as if the absolute element does not exist.

- The element is positioned relative to the nearest ancestor with a non‑static position.

- Offset properties (top, right, bottom, left) apply to the containing block.

**Example**

```html
<div class="container">
    <div class="absolute-box">Absolute</div>
</div>

<style>
.container {
    position: relative;
    width: 300px;
    height: 150px;
    background: #f1faee;
}
.absolute-box {
    position: absolute;
    top: 10px;
    right: 15px;
    background: #e63946;
    padding: 8px;
}
</style>
```

## Conclusion

-  Relative position maintains document flow with visual adjustment.
  
-  Absolute position offers precise removal from flow and pinpoint placement.


## References 

- https://www.w3schools.com/css/css_positioning.asp
