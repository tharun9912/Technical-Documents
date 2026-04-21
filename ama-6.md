# AMA-6

## 1. Files created automatically in a Django project

When you run:
`django-admin startproject projectname`

You get:

- **manage.py** → Used to run commands (runserver, migrations)
- **projectname/**
  - **__init__.py** → Marks it as a Python package
  - **settings.py** → All project settings (DB, apps, etc.)
  - **urls.py** → URL routing (maps URLs to views)
  - **asgi.py** → For async servers
  - **wsgi.py** → For deployment (Gunicorn uses this)


## 2. What is Middleware?

Middleware is a layer between request and response.

 It processes request before view and response after view.

### Example:
- Checking if user is logged in
- Adding security headers

Flow:
Request → Middleware → View → Middleware → Response


## 3. What is models.py?

- models.py is used to define database tables.

### Example:
```python
class Student(models.Model):
    name = models.CharField(max_length=100)
```

This creates a table with column "name".


## 4. Is render a function or module?

`render` is a **function**.

It is imported from:
```python
from django.shortcuts import render
```


## 5. What is Dynamic Routing?

Dynamic routing means URL contains variable values.

### Example:
```python
path('user/<int:id>/', views.user_profile)
```

URL:
`/user/5/`

Here `5` is dynamic.


## 6. What is Clickjacking?

Clickjacking is a security attack.

 A user is tricked into clicking something hidden.

### Example:
A fake button hides a real "delete account" button.


## 7. What render function is used for?

`render` is used to send HTML page to browser.

### Example:
```python
return render(request, 'home.html')
```

It combines:
- template (HTML)
- data
- request


## 8. What is Nginx and Gunicorn?

### Gunicorn:
- Python server
- Runs Django app

### Nginx:
- Web server
- Handles requests from users
- Sends them to Gunicorn

Flow:
User → Nginx → Gunicorn → Django


## 9. Difference between Static and Dynamic Files

### Static Files:
- Do not change
- Examples: CSS, JS, images

### Dynamic Files:
- Change based on data
- Example: user profile page

