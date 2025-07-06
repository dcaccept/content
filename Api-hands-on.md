# 📦 Python Requests Module Tasks with Solutions

This section evaluates your understanding and ability to work with Python's `requests` module, which is used to send HTTP requests. Each task includes a question, input, expected output, and example code for reference.

---

## 🔹 Task 1: Sending a GET Request

**Question:**  
Write Python code that sends a `GET` request to a sample API and prints the status code and response text.

**Input:**
- **URL**: `https://jsonplaceholder.typicode.com/posts/1`

**Expected Output:**
- Status Code: `200`
- Response Text: JSON content with the post details.

**Python Code:**
```python
import requests

response = requests.get("https://jsonplaceholder.typicode.com/posts/1")
print("Status Code:", response.status_code)
print("Response Text:", response.text)

```
---

## 🔹 Task 2: Sending a POST Request

**Question:**  
Write Python code to send a POST request to an API with some data and print the response.


**Input:**
- **URL**: `https://jsonplaceholder.typicode.com/posts`

**Expected Output:**
- Status Code: `201`
- Response Text: JSON content with the post details.

**Python Code:**
```python
import requests

url = "https://jsonplaceholder.typicode.com/posts"
data = {
    "title": "foo",
    "body": "bar",
    "userId": 1
}

response = requests.post(url, json=data)
print("Status Code:", response.status_code)
print("Response Text:", response.json())
