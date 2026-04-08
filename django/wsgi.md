# WSGI (Web Server Gateway Interface) 

In web development, we need a way for a web server (like Nginx or Apache) to talk to a Python application (like Django).

 WSGI (Web Server Gateway Interface) is a standard that connects web servers and Python web applications.

## What is WSGI?


WSGI is a specification (set of rules) that defines how:

 - A web server sends requests to a Python application
 
 - A Python application sends responses back to the server

Web server speaks: HTTP

Python app speaks: Python

WSGI translates between them


##  How WSGI Works

Browser → Web Server → WSGI → Django App → WSGI → Web Server → Browser

Example (Basic WSGI App)

```python
def simple_app(environ, start_response):
    status = '200 OK'
    headers = [('Content-type', 'text/plain')]

    start_response(status, headers)

    return [b"Hello, World!"]
```
 
 ### Explanation

- environ

  - A dictionary containing request data

  Example: URL, headers, method (GET/POST)

- start_response

   - A function used to send:
        HTTP status (200 OK)
        Headers

- Return value

   - return [b"Hello, World!"]
   - Response must be in bytes
   - Returned as an iterable (list)

## WSGI in Django

Django automatically creates a WSGI file:

### wsgi.py

```python
import os
from django.core.wsgi import get_wsgi_application

os.environ.setdefault('DJANGO_SETTINGS_MODULE', 'project.settings')

application = get_wsgi_application()
```

### What this does

 - Loads Django settings

 - Creates a WSGI application object
 
 - This object is used by servers like: Gunicorn and uWSGI

## Where is WSGI Used?

WSGI is used in production deployment

Example setup:

Nginx → Gunicorn → Django (WSGI)


Without WSGI:

  - Web server cannot directly run Python code

With WSGI:

  - Server sends request → WSGI → Django → response

# Why WSGI is Important

- Standard interface for Python web apps

- Works with many servers

- Makes deployment easier

- Ensures compatibility

# Summary

WSGI connects web server and Python app

It defines how requests and responses are handled

Django uses WSGI for deployment

Acts as a bridge.