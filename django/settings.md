# settings file in Django

#  1. What is SECRET_KEY in Django?


`SECRET_KEY` is a **secret string used by Django for security purposes**.

It is stored in:

```python
# settings.py
SECRET_KEY = "your-secret-key"
```

##  Why does Django need it?

Django uses `SECRET_KEY` to:

* Protect user sessions
* Sign cookies (so users cannot modify them)
* Generate CSRF tokens


##  Example

When a user logs in:

* Django creates a session
* That session is **signed using SECRET_KEY**

If someone changes the session data:

* Django detects it (because signature breaks)


##  What happens if it is leaked?

If someone gets your SECRET_KEY:

* They can **fake login sessions**
* They can **bypass security**
* They can act as another user


## Best Practice

* Use a **long random string**
* Keep it **secret**
* Store it in `.env` file .


#  2. Default Django Apps

When you create a Django project, Django automatically includes some **built-in apps**.


##  Default Apps List

```python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
]
```


##  What each app does


### 1. `django.contrib.admin`

 Provides admin dashboard

Helps to 

* Add users
* Manage products


### 2. `django.contrib.auth`

Handles authentication

Features:

* Login / Logout
* User model
* Permissions

Example:

```python
from django.contrib.auth.models import User
```

### 3. `django.contrib.contenttypes`

 Tracks all models in the project

* Used internally by Django
* Helps generic relationships

---

### 4. `django.contrib.sessions`

 Stores user session data

Example:

* Remember logged-in user


### 5. `django.contrib.messages`

Shows temporary messages representing the status of request and response etc.

Example:

```python
messages.success(request, "Login failed")
```


### 6. `django.contrib.staticfiles`

Handles static files

Examples:

* CSS
* JavaScript
* Images

---

##  Are there more apps?

 YES,there are more apps 

Django allows:

###  Custom Apps

```bash
python manage.py startapp new_app
```


###  Third-party Apps

Examples:

* `rest_framework` → Build APIs
* `django-cors-headers` → Handle CORS



#  Summary

## SECRET_KEY

* Used for security
* Must be kept secret
* Protects sessions, cookies, tokens


## Default Apps

* Built-in apps provided by Django
* Handle admin, auth, sessions, etc


