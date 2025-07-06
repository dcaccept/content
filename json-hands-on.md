
# 📦 Python JSON Module Tasks

This section evaluates your understanding and ability to work with Python's built-in `json` module. Complete each task by writing Python code. Each task includes a question, input, and expected output to help guide your solution.

# ✅ Common functions in Python `json` module

| Function      | Description                                                   |
|----------------|---------------------------------------------------------------|
| `json.load()`  | Read JSON data from a **file-like object** and convert it to a Python object. |
| `json.loads()` | Parse JSON data from a **string** and convert it to a Python object.         |
| `json.dump()`  | Serialize a Python object and write it as JSON to a **file-like object**.   |
| `json.dumps()` | Serialize a Python object and return it as a JSON **string**.               |

---

## 🔹 Task 1: Parse a JSON String

**Question:**  
You are given a string in JSON format. Convert it into a Python dictionary using an appropriate `json` function.

**Input:**
```python
json_string = '{"name": "Alice", "age": 30, "skills": ["Python", "SQL"]}'
```
**Code:**
```python
import json

data = json.loads(json_string)
print(data)
```

**Expected Output:**
```python
{'name': 'Alice', 'age': 30, 'skills': ['Python', 'SQL']}
```

---

## 🔹 Task 2: Convert Python Dictionary to JSON

**Question:**  
You are given a Python dictionary. Convert it to a JSON string using the correct method.

**Input:**
```python
data = {
    "product": "Laptop",
    "price": 850.75,
    "features": ["SSD", "8GB RAM", "i5"]
}
```
**Code:**
```python
import json

json_str = json.dumps(data)
print(json_str)

```

**Expected Output:**
```json
{"product": "Laptop", "price": 850.75, "features": ["SSD", "8GB RAM", "i5"]}
```

---

## 🔹 Task 3: Pretty Print JSON

**Question:**  
Use the appropriate json function to pretty print the given dictionary with an indent of 4 spaces.

**Input:**
```python
data = {
    "product": "Laptop",
    "price": 850.75,
    "features": ["SSD", "8GB RAM", "i5"]
}

```
**Code:**
```python
import json
pretty_json = json.dumps(data, indent=4)
print(pretty_json)
```

**Expected Output:**
```json
{
    "product": "Laptop",
    "price": 850.75,
    "features": [
        "SSD",
        "8GB RAM",
        "i5"
    ]
}

```

---

## 🔹 Task 4: Read JSON from a File

**Question:**  
Assume a file named `student.json` contains valid JSON data. Read the file and convert the content into a Python dictionary.

**File Content:**
```json
{
    "name": "Bob",
    "marks": {
        "math": 80,
        "science": 85
    }
}

```

**Code:**
```python
import json

with open("student.json", "r") as file:
    data = json.load(file)

print(data)


```

**Expected Output:**
```python
{'name': 'Bob', 'marks': {'math': 80, 'science': 85}}
```

---

## 🔹 Task 5: Write Python Dictionary to File as JSON

**Question:**  
Write the given dictionary into a JSON file named `framework.json`, formatted with an indentation of 2 spaces.

**Input:**
```python
data = {"framework": "Django", "version": 4.2}
```
**Code:**
```python
import json

data = {"framework": "Django", "version": 4.2}

with open("framework.json", "w") as file:
    json.dump(data, file, indent=2)


```

**Expected File Content:**
```json
{
  "framework": "Django",
  "version": 4.2
}
```

---

## 🔹 Task 6: Handle Invalid JSON String

**Question:**  
You are given an invalid JSON string. Write Python code to safely parse it using exception handling.

**Input:**
```python
bad_json = '{"name": "John", "age": 30,'
```
**Code:**
```python
import json

try:
    data = json.loads(bad_json)
except json.JSONDecodeError as e:
    print("Error parsing JSON:", e)

```

**Expected Output:**
```
Error parsing JSON: Expecting property name enclosed in double quotes: line 1 column 30 (char 29)
```

---

## 🔹 Task 7: Modify JSON and Save Back to File

**Question:**  
Read the content of `employee.json`, update the employee's department, and write the updated data back to the same file.

**Initial File Content:**
```json
{
  "id": 101,
  "name": "Jane",
  "department": "Sales"
}
```

**Update Requirement:** Change `department` to `"Marketing"`.

**Code:**
```python
import json

with open("employee.json", "r") as file:
    data = json.load(file)

data["department"] = "Marketing"

with open("employee.json", "w") as file:
    json.dump(data, file, indent=2)

```

**Expected File Output:**
```json
{
  "id": 101,
  "name": "Jane",
  "department": "Marketing"
}
```

---
