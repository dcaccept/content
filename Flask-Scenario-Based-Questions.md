# 🚀 Flask Module

## 🎯 Objective

Assess the candidate’s practical experience with Flask, covering basic to advanced concepts, API design, routing, error handling, and application structure.

---

## 1️⃣ Basic concepts

**Question:**  
What is Flask, and how is it different from Django?

**Expected:**
- Flask is a lightweight, micro web framework in Python.
- Minimalistic and flexible, gives more control over components.
- Django is a full-stack framework with built-in ORM, admin, and more batteries-included.

---

## 2️⃣ Routing

**Question:**  
How do you define a route in Flask that accepts both GET and POST?

**Expected:**
```python
@app.route('/example', methods=['GET', 'POST'])
def example():
    pass

---

## 3️⃣ Request and response objects

**Question:** 
How do you access JSON data sent in a POST request?

**Expected:**

python


from flask import request
data = request.get_json()

---

## 4️⃣ Error handling
Question:
How do you handle errors globally in Flask?

Expected:

Using error handler decorators, e.g.:

python


@app.errorhandler(404)
def not_found(e):
    return {"message": "Not found"}, 404

---

## 5️⃣ Blueprints
Question:
What is a Blueprint in Flask? When and why would you use it?

Expected:

Blueprint is a way to organize routes and logic into reusable modules.

Useful for large apps to separate concerns (e.g., auth, user management, admin features).

---


## 6️⃣ Configuration and environment
Question:
How would you manage different configurations (development, testing, production) in a Flask app?

Expected:

Use app.config.from_object() or environment variables.

Create separate config files like config.py, development.py, production.py.

---


## 7️⃣ Decorators and middleware
Question:
How can you create a custom decorator in Flask to check if a user is authenticated?

Expected:

python


from functools import wraps
from flask import request, abort

def require_auth(f):
    @wraps(f)
    def decorated(*args, **kwargs):
        token = request.headers.get('Authorization')
        if not token or token != "expected_token":
            abort(401)
        return f(*args, **kwargs)
    return decorated

@app.route('/secure')
@require_auth
def secure_route():
    return {"message": "Authorized access"}

---

## 8️⃣ API example exercise
Task:
Write a Flask endpoint /sum that accepts two numbers (a and b) as query parameters and returns their sum as JSON.

Expected:

python


@app.route('/sum', methods=['GET'])
def sum_numbers():
    a = int(request.args.get('a', 0))
    b = int(request.args.get('b', 0))
    return {"sum": a + b}

---

## 9️⃣ Production readiness
Question:
Is Flask suitable for direct production use? If not, what would you do?

Expected:

Flask's built-in server is not production-ready (only for development).

Should use a production WSGI server (e.g., Gunicorn, uWSGI) behind a reverse proxy (e.g., Nginx).

