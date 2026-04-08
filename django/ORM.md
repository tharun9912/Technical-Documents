# Django ORM & SQL 

 - Django provides an **ORM (Object Relational Mapper)** that allows you to interact with the database using Python instead of writing SQL queries.

 - You can test and run ORM queries using the **Django Shell**.
 
 - convert ORM queries into SQL for better understanding and debugging.


#  1. Using ORM Queries in Django Shell

##  What is Django Shell?

Django shell is an interactive Python environment where you can:

* Run ORM queries
* Test models
* Debug database operations


##  How to Open Django Shell

```bash
python manage.py shell
```

##  Example Model

```python
from django.db import models

class Person(models.Model):
    name = models.CharField(max_length=200)
    age = models.IntegerField()
```

##  Basic ORM Queries


###  Create Data

```python
Person.objects.create(name="tharun", age=23)
```

###  Get All Data

```python
Person.objects.all()
```

###  Filter Data

```python
Person.objects.filter(price__gt=10000)
```

 `__gt` means greater than


###  Get Single Object

```python
Person.objects.get(id=1)
```


###  Update Data

```python
p = Person.objects.get(id=1)
p.price = 60000
p.save()
```

###  Delete Data

```python
p = Person.objects.get(id=1)
p.delete()
```


##  Common Query Filters

| Query                  | Meaning       |
| ---------------------- | ------------- |
| `price__gt=100`        | greater than  |
| `price__lt=100`        | less than     |
| `name__contains="lap"` | contains text |
| `id__in=[1,2,3]`       | match list    |



#  2. Turning ORM into SQL in Django Shell


##  Why convert ORM to SQL?

* To understand what Django is doing internally
* To debug slow queries
* To learn SQL from ORM


##  Method 1: Using `.query`

```python
queryset = Product.objects.filter(price__gt=1000)
print(queryset.query)
```

---

### Output (SQL)

```sql
SELECT * FROM person WHERE age > 18;
```

##  Method 2: Using `str()`

```python
str(Person.objects.all().query)
```

#  Example: ORM vs SQL


## ORM Query

```python
Person.objects.filter(name__icontains="th")
```

## Equivalent SQL

```sql
SELECT * FROM Person WHERE name LIKE '%th%';
```

---

#  Important 

##  Lazy Evaluation

 ORM queries are not executed immediately

```python
qs = Person.objects.all()  # No DB hit
list(qs)  # Now DB hit happens
```

---

##  QuerySet

* A collection of database queries
* Can be filtered, chained, reused

# Key Benefits

* No need to write raw SQL
* Database-independent
* Faster development



#  Summary


## ORM in Django Shell

* Used to interact with database using Python
* Supports CRUD operations
* Easy and readable


## ORM to SQL

* Use `.query` to see SQL
* Helps debugging and learning



