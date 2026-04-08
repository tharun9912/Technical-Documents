# Django Models 

In Django, the **models file** is used to define the structure of your database.

#  1. What is Models File in Django?

The `models.py` file is where you define **database tables using Python classes**.

 Each class = Table
 Each attribute = Column


## Example

```python
from django.db import models

class Product(models.Model):
    name = models.CharField(max_length=200)
    age = models.IntegerField()
    in_stock = models.BooleanField()
```

#  2. What is on_delete=CASCADE?


`on_delete=models.CASCADE` means:

 If the **parent object is deleted**, all related child objects will also be deleted.


##  Example

```python
class Category(models.Model):
    name = models.CharField(max_length=100)

class Product(models.Model):
    name = models.CharField(max_length=100)
    category = models.ForeignKey(Category, on_delete=models.CASCADE)
```

##  What happens?

If you delete a category:

```python
Category.objects.get(id=1).delete()
```

 All products in that category are also deleted automatically.


##  Other options 

| Option      | Meaning           |
| ----------- | ----------------- |
| CASCADE     | Delete child data |
| SET_NULL    | Set value to NULL |
| PROTECT     | Prevent deletion  |
| SET_DEFAULT | Set default value |


#  3. Fields in Django Models

Fields define **data types of columns**.


##  Common Fields

###  CharField

```python
name = models.CharField(max_length=100)
```

 used for short text

### TextField

```python
description = models.TextField()
```
used for long text


###  IntegerField

```python
age = models.IntegerField()
```

###  FloatField

```python
price = models.FloatField()
```

###  BooleanField

```python
is_active = models.BooleanField()
```

### DateTimeField

```python
created_at = models.DateTimeField(auto_now_add=True)
```

###  ForeignKey

```python
category = models.ForeignKey(Category, on_delete=models.CASCADE)
```

 Creates relationship between models


# 4. Validators in Django

Validators are used to **validate data before saving**.


##  Example

```python
from django.core.validators import MinValueValidator, MaxValueValidator

class Product(models.Model):
    price = models.FloatField(
        validators=[MinValueValidator(0)]
    )
```

 Ensures price is not negative

##  Why Validators?

* Prevent invalid data
* Improve data quality
* Reduce bugs


#  5. Python Module vs Python Class

##  What is a Module?

 A module is a **Python file (.py)**

Example:

```python

def greet():
    print("Hello")
```

Usage:

```python
import utils
utils.greet()
```

##  What is a Class?

 A class is a **blueprint for creating objects**

Example:

```python
class Person:
    def __init__(self, name):
        self.name = name

    def say_hello(self):
        print("Hello", self.name)
```

Usage:

```python
p = Person("Tharun")
p.say_hello()
```

#  Summary

- Models define database structure using Python classes

- on_delete=CASCADE deletes related data automatically

- Fields define column types

- Validators ensure correct data input

- Module = file, Class = blueprint for objects