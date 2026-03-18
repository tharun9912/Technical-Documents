# Why Using Global Variables is Bad in JavaScript ?

  - global variable is a variable that is declared outside any function or block, so it can be accessed from anywhere in the program.

     Example:

    ```javascript
    let count = 0; // global variable

      function increase(){
       count++;  
       }
    ```

## Bad practice to use, because

  ### - 1. Risk of Accidental Modification

   - Since global variables can be accessed anywhere in the program, any function can change their value, which may cause unexpected results.


 ```javascript
    
       let total = 100;

        function add(){
             total = total + 50;
         }

       function reset(){
          total = 0;
        }

       add();
       reset();

       console.log(total);
 ```

 
- Both functions modify the same variable.

 - This can cause unexpected behavior if many functions change the same variable.

### 2. Variable Name Conflicts

  - Global variables increase the chances of naming conflicts when multiple  parts of a program use the same variable name.

  ```javascript
  let user = "Admin";

   function login(){
      let user = "Guest";
    }
  ```

  - In large projects, another developer might also create a variable called user, which can create confusion or bugs.

### 4. Hard to Debug

   - When a global variable is changed in many places, it becomes difficult to track where the value was modified.


  ```javascript

    let score = 0;

    function gameStart(){
        score = 10;
     }

    function gameEnd(){
       score = 0;
    }
  ```

  - If the score changes unexpectedly, it becomes hard to find which function changed it.


### 5 Memory Usage Issues.

 - Global variables remain in memory for the entire lifetime of the   program, even if they are no longer needed.

  Example:

 ```javascript
    let largeData = [/* huge dataset */];
 ```
- This can lead to wasted memory in large applications.

