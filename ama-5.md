# Django Basics 

## 1. What is `models.py`?

* It defines the **structure of your database tables**.
* You write Python classes, and Django converts them into database tables.

### Example:

```python
from django.db import models

class Student(models.Model):
    name = models.CharField(max_length=100)
    age = models.IntegerField()
```

 This creates a table `Student` with columns `name` and `age`.


## 2. What is Middleware?

* Middleware is something that runs **between request and response**.
* It can modify request or response.

### Example:

* Logging user requests
* Checking authentication


## 3. What is WSGI?

* WSGI stands for **Web Server Gateway Interface**.
* It connects your Django app with the web server.

 
## 4. What is Jinja?

* Jinja is a **template engine**.
* It helps to display dynamic data in HTML.

### Example:

```html
<h1>{{ name }}</h1>
```

 `{{ }}` is used to print variables.

## 5. What is MVT?

* MVT = **Model, View, Template**

### Flow:

1. Model → handles data
2. View → business logic
3. Template → UI (HTML)


## 6. How to hide SECRET KEY?

* Store it in `.env` file instead of settings.py

### Example:

SECRET_KEY=your_secret_key_here
```

In `settings.py`:

```python
import os
SECRET_KEY = os.getenv("SECRET_KEY")
```

## 7. How apps run in Django?

* Django project contains multiple apps
* Apps are registered in `INSTALLED_APPS`

### Flow:

Request → URL → View → Model → Template → Response


## 8. What is Migration?

* Migration is used to **apply changes to database**

### Commands:

```bash
python manage.py makemigrations
python manage.py migrate
```

## 9. What is `Sum` method?

* Used to calculate total in Django ORM

### Example:

```python
from django.db.models import Sum

Order.objects.aggregate(total=Sum('price'))
```


## 10. What is Namespace in Django?

* Used to **avoid URL name conflicts**

### Example:

```python
app_name = 'blog'
```

```html
<a href="{% url 'blog:home' %}">Home</a>
```

## 11. What is `settings.py`?

* Main configuration file of Django project

### Contains:

* Installed apps
* Database config
* Middleware
* Secret key


## 12. Default database in Django

* SQLite is default database

 File: `db.sqlite3`


## 13. What is `urls.py`?

* It maps URLs to views

### Example:

```python
from django.urls import path
from . import views

urlpatterns = [
    path('', views.home, name='home'),
]
```

 When user opens URL → corresponding view runs
