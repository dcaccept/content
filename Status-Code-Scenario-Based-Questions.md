# ✅ HTTP Status Codes & Error Handling Module

## 🎯 Objective

Assess candidate’s understanding of common and edge-case HTTP status codes, and how they design robust error handling in real-world API scenarios.

---

## 1️⃣ Common success and error codes

**Question:**  
What is the difference between status codes 200, 201, and 204? When would you use each?

**Expected:**
- 200 OK: Successful GET, or general success with a body
- 201 Created: Resource successfully created (POST), usually returns location header
- 204 No Content: Successful operation, no response body (e.g., DELETE or update with no content)

---

## 2️⃣ Client error codes

**Question:**  
What do status codes 400 and 422 mean? When would you return each?

**Expected:**
- 400 Bad Request: Malformed syntax or invalid request data
- 422 Unprocessable Entity: Semantically correct request, but invalid or unprocessable data (common with validation errors in REST APIs)

---

## 3️⃣ Authentication and authorization codes

**Question:**  
Explain when to use 401 vs 403.

**Expected:**
- 401 Unauthorized: Missing or invalid authentication (user is not logged in or token is invalid)
- 403 Forbidden: Authenticated, but no permission to access the resource

---

## 4️⃣ Rate limiting or throttling

**Question:**  
Which status code would you return if a user exceeds allowed API request limits?

**Expected:**
- 429 Too Many Requests

---

## 5️⃣ Resource conflicts

**Question:**  
When would you return a 409 Conflict?

**Expected:**
- Resource already exists or there’s a conflict with the current state (e.g., creating a user that already exists)

---

## 6️⃣ Redirect codes

**Question:**  
Name two redirect status codes and when they are used.

**Expected:**
- 301 Moved Permanently: Resource moved permanently, client should update URL
- 302 Found (or 307 Temporary Redirect): Temporary redirect, client may continue to use original URL

---

## 7️⃣ Server errors

**Question:**  
What is the meaning of 500 and 503 codes?

**Expected:**
- 500 Internal Server Error: Generic server error (unexpected condition)
- 503 Service Unavailable: Service is temporarily unavailable (maintenance or overloaded)

---

## 8️⃣ Status codes and REST principles

**Question:**  
Why is it important to return accurate HTTP status codes in APIs?

**Expected:**
- Helps clients handle responses correctly (retry, display message, fallback)
- Improves observability and debugging
- Aligns with REST principles (stateless, uniform interface)

---

## 🔎 Bonus practical exercise

**Task:**  
Write a small Flask (or FastAPI) endpoint that returns:
- 200 when the input parameter `status` = "ok"
- 400 when `status` = "bad"
- 500 for anything else

**Sample solution (Flask):**
```python
from flask import Flask, request, jsonify

app = Flask(__name__)

@app.route("/check", methods=["GET"])
def check_status():
    status = request.args.get("status")
    if status == "ok":
        return jsonify({"message": "All good!"}), 200
    elif status == "bad":
        return jsonify({"message": "Bad request!"}), 400
    else:
        return jsonify({"message": "Unexpected error!"}), 500

if __name__ == "__main__":
    app.run(debug=True)
