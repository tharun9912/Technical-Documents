
**1. What is Grid?**
  
  - CSS Grid is a layout system used to arrange elements in rows and columns.

  Example:

  ```css
     .container
     {
         display: grid;
         grid-template-columns: 1fr 2fr;
     }
  ```

**2. Property used to align center**

 - To center items in CSS:
    
    - Flexbox
    - justify-content: center;
    - align-items: center;

 - Grid

    - place-items: center;

**3. Different values in color property**

   - Ways to give color:

   - Color name
     ```css
      color:blue;
     ```
   - Hex
    
     ```css
     color: #ff0000;
     ```

   - RGB
      ```css
       color: rgb(255,0,0);
      ```
   - HSL
     ```css
       color: hsl(0,100%,50%);
     ```
**4. Display properties**

   - Common display values:
      - block
      - inline
      - inline-block
      - flex 
      - grid
      - none

   ```css
   display:inline;
   ```
**5. Which CSS has most importance (Priority)**

  - Priority order:
    - !important
 
    - Inline CSS

    - Internal CSS
 
    - External CSS

**6. Use of form tag**

  - The form tag is used to collect user input.

  - Example inputs:

     - name

     - email

     - password

     - number

 -Syntax:

```css
      <form>
         <input type="text">
         <input type="email">
      </form>
```
**7.Explain Open Closed Principle?.**

  -  SOLID principles.

  - Open closed principle is defined as a class should be open for extension but closed for modification.

  - You can add new features without changing existing code

**8. Difference between Container and Media Query**

   - Container Query

      - Wraps content
      
      - Controls width and layout

      - Syntax
  
      ```css
        .container{
           width: 1200px;
           margin: auto;
          }
      ```
   - Media Query
     
      - Used for responsive design,changes style based on screen size.

      ```css
      @media (max-width:480px){
            body{
              background:green;
            }
        }
      ```

      ```css
      @media (min-width:1024px){
        body{
         background:red;
        }
       }
      ```

**9. Z-index**

 - z-index controls which element appears on top.

 - Higher value = appears above.

 - Example:

 ```css
    box1
    {
     z-index: 1;
    }
 ```

 ```css
    box2
    {
      z-index: 10;
    }
 ```

 here box2 appears on top.

**10. Flexbox**

  - Flexbox is a layout system used to align items in one direction (row or column).

  - Example:

  ```css
     .container
     {
      display: flex;
     }
  ```
  - Used for alignment and spacing.

**11.Difference between justify-content and align-content**

   - justify-content used for horizontal alignment of elements.
   
   - align-content iused for vertical alignment.

   - Example:

     ```css
        justify-content: center;
        align-content: center;
     ```

**12. Types of gaps**

  - In Grid and Flex,gaps are row-gap,column-gap
  
  - Example
  
   ```css
     gap: 35px;
     row-gap: 5px; 
     column-gap: 10px;
   ```

**13. Box sizing**

  - Controls how width and height are calculated.
 
  - It involves 

     - content-box (default)
     
     - border-box
  
  - Example

  ```css
    box-sizing: border-box;
  ```
  - This includes padding and border inside width.

**14.Way to access child  element directly from parent**

  - Use child selector >

  - Example:

  ```css
      div > p
      {
        color: red;
      }
   ```
  - It selects only direct children.

**15. Different types of CSS units**

   - Absolute CSS units are

       - px
       - cm
       - mm

   - Example

     ```css
      width: 200px;
     ```
- Relative units

    -   %
    - em
    - rem
    - vw
    - vh

  Example
  ```css
    width: 50%;
    font-size: 3rem;
  ```