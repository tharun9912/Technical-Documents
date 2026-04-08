# Django Middleware 

Middleware acts as an intermediate layer that can modify, inspect, or reject requests before they reach the application logic (views), and also process responses before sending them back to the client.


# What is Middleware?


Middleware is a **function or class that sits between the client request and the Django view**.

It processes:

* Incoming requests
* Outgoing responses


##  Request–Response Lifecycle   

```
Client → Middleware → View → Middleware → Client
```

## Example

```python
def simple_middleware(get_response):
    def middleware(request):
        print("Before view execution")

        response = get_response(request)

        print("After view execution")
        return response

    return middleware
```

### Explanation:

* Before the view runs → middleware executes first
* After the view returns → middleware executes again


#  Types of Middleware in Django

Django provides several built-in middleware components.


##  1. Security Middleware

```python
'django.middleware.security.SecurityMiddleware'
```

### Purpose:

* Adds security headers
* Enforces HTTPS

### Example:

```python
SECURE_SSL_REDIRECT = True
```

 Redirects HTTP requests to HTTPS


##  2. CSRF Middleware

```python
'django.middleware.csrf.CsrfViewMiddleware'
```

###  Security Issue: CSRF (Cross-Site Request Forgery)

### Problem:

An attacker tricks a logged-in user into making unwanted requests.

### Example:

* User logs into bank
* Malicious site sends request to transfer money


### Solution:

Django uses **CSRF tokens**

```html
<form method="POST">
  <input type="hidden" name="csrfmiddlewaretoken" value="secure_token">
</form>
```


##  3. XSS (Cross-Site Scripting)

###  Security Issue:

Injection of malicious JavaScript into web pages.

### Example:

```html
<script>alert("Hacked")</script>
```


### Solution:

Django automatically escapes user input

```html
{{ user_input }}
```

##  4. Clickjacking Protection

```python
'django.middleware.clickjacking.XFrameOptionsMiddleware'
```

###  Security Issue:

User is tricked into clicking hidden elements inside an iframe.



### Solution:

```python
X_FRAME_OPTIONS = 'DENY'
```

 Prevents embedding your site in iframes

##  5. Session Middleware

```python
'django.contrib.sessions.middleware.SessionMiddleware'
```

### Purpose:

* Handles user sessions
* Stores login state


##  6. Message Middleware

```python
'django.contrib.messages.middleware.MessageMiddleware'
```

### Purpose:

* Displays temporary messages to users

Example:

```python
messages.success(request, "Login successful")
```


##  7. Common Middleware

```python
'django.middleware.common.CommonMiddleware'
```

### Purpose:

* URL normalization
* Adds trailing slashes

Example:

```
/contact → /contact/
```


#  Security Issues 


##  CSRF (Cross-Site Request Forgery)

* Fake request sent without user knowledge
* Protected using CSRF tokens


##  XSS (Cross-Site Scripting)

* Malicious scripts injected into pages
* Prevented by auto-escaping


##  Clickjacking

* Hidden UI tricking user clicks
* Prevented using frame restrictions



#  Summary

Middleware is a critical component in Django that:

* Controls request and response flow
* Adds reusable functionality
* Enhances application security

It plays a key role in protecting applications from common web vulnerabilities such as CSRF, XSS, and clickjacking.


