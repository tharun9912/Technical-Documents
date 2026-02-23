# Python

## List Methods

numbers=[1,2,3,4]

- append()	   
  - Add one element at end	
  - numbers.append(5)
  
- extend()
  - Add multiple elements
  - numbers.extend([6,7,8])
  
- insert()
  - Insert at specific index
  - numbers.insert(11, 10)
  
- pop()
  - Removes last element
  - numbers.pop()
  
- remove()
  - Remove specific value
  - numbers.remove(3)

- sort()
  - sort list
  - numbers.sort()

- len()
  - get length
  - len(numbers)
  
## String Methods

name="gonchi"

- upper()
  - Convert to uppercase
  - name.upper()
  
- lower()
  - Convert to lowercase
  - name.lower()

- strip()
  - Remove spaces
  - name.strip()

- replace()
  - Replace text
  - name.replace("g","r")

- split()
  - Convert string to list
  - "a,b,c".split(",")

- join()
  - Join list into string
  - ",".join(["a","b"])

## Objects and Object Oriented Programming

- In object oriented programming we create objects and classes.
  
### Class

- Blueprint for creating objects.

``` bash 
    Class Employee:
       def __init__(self,name):
            self.name=name 
```
### Object

- Instance of a class.
  
``` bash 
        e1 =Employee("Tharun")
```
### OOP Principle


-  Inheritance
   - Child class uses parent class.

- Encapsulation 
  - Hiding data inside the class.

- Abstraction 
  - Showing only necessary details.

- Polymorphism
  - Performing multiple functions with same function.


### Decorators

- Decorator is a function that adds extra functionality to another function without modifying its original code.

**Example:**

```bash
def decorator_func(func):
    def wrapper():
        print("Before function")
        func()
        print("After function")
    return wrapper

@decorator_func
def greet():
    print("good morning")
```

**output**:

```bash
Before function
good morning
After function
```

### Virtual Environment

- It is an isolated environment in system.
- It allows different projects to use different package versions and avoids conflicts.
  
**creation of virtual environment**

```bash
python -m venv venv
```
**Activation of Virtual Environment** 
```bash
source venv/bin/activate
```
**Deactivation**
```bash
deactivate
```

### Pip Package Manager

- pip is the package manager for Python.
  
Example :
```bash
pip install numpy
pip uninstall requests
pip list
pip freeze
```

### PEP-8 Standards Summary

- PEP 8 is the Python coding style guide.

**Rules**

- **Naming**
  - Variables should be in snake_case
  - Classes should be in camelcase
  - constant should be in upper case.
- **Indentation** 
  - Should have 4 spaces.
- **Line Length**
  - Maximum 79 characters

**Imports**

- At top of file.
- One per line.
  
