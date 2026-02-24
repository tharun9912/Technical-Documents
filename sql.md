# SQL

## ACID properties

- ACID is a set of rules that makes sure database transactions are safe, correct, and reliable.
  ### Atomicity
  - A transaction must complete fully or not at all.
  
  - If one operation fails, the entire transaction is rolled back.
  
  - **Example** :- While transferring money from account A to account B ,even last step fails,entire transaction fails. 
  
  ### Consistency
    - Consistency means the database always stays correct and follows all rules after a transaction.
  
    - **Example** :- After transaction, amount should be added to balance in account B.
  ### Isolation
  
    - Multiple transactions should not interfere with each other.
  ### Durability
  
    - Once transaction is committed, it remains saved permanently.
  
    -**Example** :- If system shutdown after transaction,history should be saved.
## CAP Theorem

  - The CAP theorem applies to distributed systems (multiple computers work together).
  
    - **consistency** :- All nodes return the same data.
  
    - **Availability** :- Available at all time .
  
    - **Partiotion Tolerance** :- System works despite of network failures.
  
   - A distributed system can guarantee only two out of three properties at the same time.

## Joins

- Joins combine data from multiple tables using related columns.
  
  **INNER JOIN**
  - Return matching rows only.
  ```bash
  SELECT * FROM orders INNER JOIN customers
  ON orders.customer_id = customers.id;
  ```
 **LEFT JOIN**
 - Returns all rows from left table and matching rows from right table.
 ```bash
 SELECT * FROM orders LEFT JOIN customers ON order.customer_id = customer.id; 
 ```
**RIGHT JOIN**
- Returns all rows from right table and matching rows from left.
```bash
SELECT * FROM orders RIGHT JOIN customers ON order.customer_id = customer.id; 
```
**FULL JOIN**
- Returns all rows from both tables (matched or not).

## Aggregations and Filters

### Aggregations

- Aggregate functions takes multiple rows of data and returns single value as result.
  
- COUNT() 
   -  Count rows.

- SUM()  
   -  Calculates total value.

- AVG() 
   -  Calculates average.

### Filters
    
  - **WHERE**  :-  Filters rows before grouping.
  ```bash
    SELECT * FROM Students WHERE age < 18;
  ```
  - **HAVING** :-  Filters rows after grouping.
  ```bash
  SELECT department, COUNT(*) FROM Students GROUP BY department HAVING COUNT(*) > 5;
  ```
## Normalizations

- Normalization is the process of organizing data to reduce redundancy.

- Avoids duplicate data and improve data integrity.

- **First Normal Form(1NF)** :-  No repeating groups and should not contain multiple values in a single column. 

- **Second Normal Form(2NF)** :-  Must be in 1NF and column should depend on entire composite primary key, not on part of primary key **(Partial dependency)**.
  
- **Third Normal Form(3NF)** :- Must be in 2NF and no transitive dependency.
  
## Indexes 

- Indexes improves query performance.
- It makes searching data faster.

**Types of Indexes** :

   - B-tree, data stored in sorted tree structure and uses binary search.

   - Hash.

   - Composite index

   - Unique index

 **Example**
 ```bash
 CREATE INDEX id_students_index ON Students(id);
 ```
## Transactions

- A transaction is a group of database operations that are treated as one single unit.

- Either all the operations happen, or none of them happen.

- Even if a single operation fails,entire transaction fails.
  
**Example** 

```bash
BEGIN;

UPDATE account SET balance = balance - 100 WHERE id = 1;
UPDATE account SET balance = balance + 100 WHERE id = 2;

COMMIT;
```
- **ROLLBACK** is used to undo changes made in a transaction. It is generally used if something fails.
  
## Locking Mechanism

- Locking is a mechanism that prevents multiple users from modifying the same data at the same time. 

- Multiple modifications at same time may create conflicts.
  
- Locking keeps data safe and controls concurrent access to avoid conflicts.
  
### Types of Locks

**Row Level Locking**

- Locks only specific rows.
  
- This allows multiple users to work on different rows at the same time.  
  
```bash
 UPDATE accounts SET balance = balance - 1000 WHERE id = 1;
```
Only row with id=1 is locked in this example.

**Table Level Locking**

- Locks the entire table.

```bash
ALTER TABLE students ADD COLUMN age INT;
```  

- Whole table is locked during operation.

**Shared Lock**

  -  Allows reading but prevents modification.

  -  used when using "SELECT" .
  
## Database Isolation levels

- Isolation levels control visibility of uncommitted data.

  **Read Uncommitted**
  
  -  Can see uncommitted changes

  **Read Committed**

  - Can only see committed data.

  **Repeatable Read**

  - Rows read cannot change during transaction
  
## Triggers

- A trigger is a special function that automatically runs when a certain event happens in a table.

- It runs when INSERT, UPDATE, or DELETE happens. 

- Triggers are commonly used for auditing changes, enforcing business rules,
  validating data.

 ### Types Of Triggers

  **Based on Timing** 
  - **Before Trigger** :- Executes before insert,update or delete operations.

  - **After Trigger** :- Executes after the operation is completed.
 
### Basic Trigger Syntax

```bash
CREATE OR REPLACE FUNCTION deleting_name()
RETURNS TRIGGER AS $$
BEGIN
    DELETE FROM Employees where name="Tharun";
    RETURN NEW; 
END;
$$ LANGUAGE plpgsql;
```
### When Not To Use Triggers

- When performance is critical.

- When logic needs transparency.
  
