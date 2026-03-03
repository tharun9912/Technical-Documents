# CSS Specificity

- CSS specificity decides which CSS rule will apply when multiple rules target the same element. 

## Importance of CSS Specificity

- Prevents css conflicts.

- Specificity keeps code clean and maintainable.

## How specificity works

- Specificity follows a priority order.

    **Priority Order**(Highest to Lowest)

    ### 1. ! important
      
     - Anything with **!important** overrirdes everything else.
 
    ```css
         p{
             color:blue !important;
          }
    ```  
    - Use only when absolutely necessary.
    
    ### 2. Inline Styles
   
   -  Styles  written directly inside HTML elements.

  ```html       
         <p style="color:red;">Hello</p>
  ```
   - Inline styles override IDs,classes and elements.
    
    ### 3. ID selectors

    - An ID selector has high specificity.

    - IDs are stronger than classes and element selectors.

   ### 4. Class,Attribute and pseudo-class selectors

   - It includes 

     - .class
     - [type="text"]
     - :hover
     - :focus
   
   ```css
     .container {
         color: red;
      }
   ```

   ### 5. Element and Pseudo-element selectors

   - It includes

     - p
     - div
     - section
     - ::before
     - ::after
   
   ```css
   p
   {
    color:blue;
   }
   ```

  ### 6. Universal selector

  - Represents with *.

  - The universal selector (*) has no specificity weight value

## Specificity Calculation Method

- CSS calculates specificity as 

```
  Inline -1000
  ID     -100
  Class  -10
  Element- 1
  Universal Selector - 0
``` 
- Example :- 

```css
#box .item p{
    color:red;
}
```

- Here #box=100, .item=10  and p=1 then total value will be 111.

- If specificity is equal,the rule written last applies.

## Best practices 

- Prefer class selector over IDs.

- Keep selectors simple.

- Avoid !important when possible.


## Conclusion

- CSS Specificity decides which style rule applies.

- Inline styles have highest priority.

- ID selectors are stronger than classes.

- Classes are stronger than element selectors.

- If specificity is equal, the last rule wins.

- !important overrides everything but should be avoided.

## References

- https://www.w3schools.com/css/css_specificity_hierarchy.asp