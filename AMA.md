# AMA

**1. What is Interface Segregation Principle (SOLID).**
  - A class should not be forced to implement on functions it does not need.

  ```bash
  class robot:
    def print(self):
        print("Printing...")
    def eat:
        print("eating")
 ```
- here robot is forcing to implement eat function which is not necessary.


**2.Explain Dependency Inversion Principle (SOLID)**? 
  - High level modules should not depend on low level modules.
  - Both should depend on abstractions.

  ```bash
  class Keyboard:
    def type(self):
        print("Typing...")

class Computer:
    def __init__(self, device):
        self.device = device

pc = Computer(Keyboard())
  ```
**3. Explain A in ACID properties ?**

 - Atomicity means a transaction either completes fully or does not happen at all (all or nothing).
- **Example :** A class named robot should not force to perform a function called  "eat" .

**4. Constructor in OOPS**

 - A constructor is a special method that initializes object data when an   object is created.
  
  ```bash
  class Student:
    def __init__(self, name):
        self.name = name

s = Student("Tharun")
print(s.name)
  ```
  
 - We use __init__ method to define constructor in python.

**5. What is a Class?**

 - A class is a blueprint or template used to create objects.

**6. CASE in SQL**

  - CASE is used for conditional logic in SQL queries, similar to if-else statements.

  - **Syntax**:
  ```bash
  SELECT name,
CASE 
   WHEN marks >= 40 THEN 'Pass'
   ELSE 'Fail'
END
FROM students;
  ```  
**7. How to create Temporary Tables in SQL?.**

- Temporary tables store data temporarily during a session and are automatically deleted after the session ends.

```bash
CREATE TEMP TABLE temp_data (
   id INT
);
```
**8.Explain types of joins in SQL?**

 - Joins combine rows from two or more tables based on a related column.

 - Types of joins are inner join, self join,left outer join,right outer join.

**9.What is nested Query in SQL?**

 - A nested query (subquery) is a query written inside another SQL query.

**10. Why Use NOT NULL in SQL?**

 - NOT NULL ensures that a column cannot store NULL (empty) values.

**11. Aggregate Functions in SQL**

- Aggregate functions perform calculations on multiple rows and give single row as output.

- Aggregate functions perform calculations on multiple rows, like SUM, COUNT, AVG, MAX, and MIN.

**12. Explain indexing in SQL?.**

 - Indexing improves query performance by allowing faster data retrieval.

**13. Decorator in Python**

 - A decorator is a function that modifies or enhances another function without changing its code.

**14 Pillars of OOPS**

  - **Encapsulation** - Hiding data and controlling access to it. 
  
  - **Abstraction** -  Showing only important detailsn and hiding complex logic.
  
  - **Inheritance** - one class inheriting properties of another class.
  
  - **Polymorphism** : Use same method name but performs different functionality.

**15.Types of Constraints**

  - Common SQL constraints are NOT NULL, UNIQUE, PRIMARY KEY, FOREIGN KEY, CHECK, and DEFAULT.

**16 . Is hiding constructor possible in python?**

 - No, constructor hiding is not possible in python.