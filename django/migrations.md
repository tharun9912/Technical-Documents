# Migration Files in Django 

- In Django, a **migration file** is used to apply changes to the database.

- Whenever we create or update models, Django needs a way to update the database structure. Migration files help us do that.


## What is a Migration File?

A migration file is:
 A file that tells Django **what changes to make in the database**

These changes include:
- Creating tables
- Adding fields
- Deleting fields
- Updating columns


## Why is it Needed?

Without migrations:
- Database will not match your models
- Your app may break

So migrations help to:
- Keep database in sync with models
- Track changes step-by-step
- Apply or undo changes easily


## Example

### Step 1: Create Model

```python
class Person(models.Model):
    name = models.CharField(max_length=100)
```

### Step 2: Create Migration

Run command:
```
python manage.py makemigrations
```

 This creates a migration file.


### Step 3: Apply Migration

Run command:
```
python manage.py migrate
```

 This creates the table in the database.


## Example Migration File

```python
class Migration(migrations.Migration):

    operations = [
        migrations.CreateModel(
            name='Person',
            fields=[
                ('id', models.AutoField(primary_key=True)),
                ('name', models.CharField(max_length=100)),
            ],
        ),
    ]
```

---

## What Happens Internally?

- Django converts models into SQL queries
- Executes queries in database
- Updates schema


## Types of Changes Migrations Handle

- Create model
- Add field
- Remove field
- Alter field


## Useful Commands

Create migration:
```
python manage.py makemigrations
```

Apply migration:
```
python manage.py migrate
```

Undo migration:
```
python manage.py migrate app_name zero
```


## Summary

- Migration file gives instructions to update database
- Keeps models and database in sync
- Easy to apply and rollback changes