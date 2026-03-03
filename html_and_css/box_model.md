# Box Model

## Introduction

- Every HTML element is treated like a box.

- It defines how elements take space on a webpage.
  
## Parts of the Box Model

- There are 4 layers in box model. They are **Content**,**Padding**,**Border**,**Margin**.

### Content

- The actual text, image, or data inside the element.

- Can give width and height to the content.

### Padding

- Space between content and border.
  
  **Ex :-**  padding:20px;

### Border

- Line surrounding padding and content.
  
- Can have width style and color.
  
  **Ex :-** border:2px solid red;  

### Margin

- Outer space between elements.

- Creates distance from other elements.

- Background color does NOT apply to margin.

  **Ex :-** margin:10px;

## Total width calculation

- By default browsers use : 
  
  **box-sizing: content-box;**

 ```
    width:200px;
    padding:10px;
    border:5px solid red;
 ```
- Then total width = content + padding + border
  
  here total width= 200px + 20px +10px = 230px;

- Here width increased to 230px because padding and border are added.

## Border Box

- Modern method ,padding and border are included inside width (here 200px).

- Prevents overflow problems.

  **Ex:- box-sizing : border-box;**

## Conclusion

- Every html element is a box.

- The box model has content,padding,border and padding.

- Default box model increases size.

- The border-box makes layouts easier.

## References

- https://www.w3schools.com/css/css_boxmodel.asp