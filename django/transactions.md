#  Transactions and Atomic Transactions 

In database systems, we often perform multiple operations such as:
- Insert data  
- Update data  
- Delete data  

These operations must be handled carefully to avoid data errors.  
To solve this problem, databases use **transactions**.


##  What is a SQL Transaction?

A SQL transaction is:

 A **group of one or more database operations** treated as a single unit.

###  Key Idea:

- Either **all operations are successful**
- Or **none of them are applied**


##  Why Do We Need Transactions?

Transactions help to:
- Keep data **safe**
- Maintain **consistency**
- Avoid **partial updates**
- Handle **failures properly**

##  Example

###  Bank Transfer

You want to transfer ₹1000 from Account A to Account B.

Steps:

1. Deduct ₹100 from Account A  
2. Add ₹100 to Account B  

###  Problem:
If step 1 succeeds but step 2 fails → money is lost.

###  Solution:

Use a transaction:
- If both steps succeed → save  
- If any step fails → undo everything  


##  SQL Transaction Example

```sql
BEGIN;

UPDATE accounts SET balance = balance - 100 WHERE id = 1;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;

COMMIT;
```
### What if Something Goes Wrong?

ROLLBACK;

 This will undo all changes made in the transaction.


## What are Atomic Transactions?

Atomic means: All or nothing

An atomic transaction ensures:

If one operation fails → entire transaction fails

No partial changes are allowed

### Atomic Transaction Example

Without Atomic Transaction:

₹100 deducted from Account A

₹100 not added to Account B

 Data becomes incorrect

 With Atomic Transaction:

Either both operations succeed

Or both are cancelled

 Data remains correct


###  Example (Atomic Transaction)

```python
from django.db import transaction

with transaction.atomic():
    deduct_money()
    add_money()
```

What happens:

If both functions work → changes saved

If any error occurs → all changes rolled back

 Using Transactions:

If payment fails → no order
If order fails → refund payment

## ACID Properties 

Transactions follow ACID properties:

1. Atomicity
   - All or nothing

2. Consistency
   - Data remains correct before and after transaction

3. Isolation
   - Transactions do not interfere with each other

4. Durability
   - Once saved, data is permanent

## When to Use Transactions?

Use transactions when:

Performing multiple related operations

Working with financial data

Handling critical updates

## Advantages

Prevents data loss

Maintains consistency

Easy error handling

Supports rollback

## Final Summary

Transaction represents group of operations

Atomic means all operations succeed or fail together

Ensures safe and reliable database operations

Uses commands like BEGIN, COMMIT, and ROLLBACK