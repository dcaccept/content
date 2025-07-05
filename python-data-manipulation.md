
# 🧠 Python Data Manipulation Task

This multi-step coding challenge is designed to evaluate your understanding of Python's core data manipulation tools. Each task builds on the previous one. Follow along step-by-step and complete each block.

---

## 🔹 Task 1: Clean and Split Input Data

**Objective:** Use `split()` and `strip()` to process raw strings into usable lists.

```python
# Input data
names_input = "  Alice, Bob, Charlie,  David  "
scores_input = " 65 40 75 49 "

# Clean and split the names
names = [name.strip() for name in names_input.strip().split(',')]

# Clean and convert scores to integers
scores = list(map(int, scores_input.strip().split()))

print("Names:", names)
print("Scores:", scores)

Names: ['Alice', 'Bob', 'Charlie', 'David']
Scores: [65, 40, 75, 49]

```

---

## 🔹 Task 2: Pair Names and Scores

**Objective:** Use `zip()` to combine names and scores into tuples.

```python
# Pair names and scores
student_pairs = list(zip(names, scores))
print("Student Pairs:", student_pairs)

Student Pairs: [('Alice', 65), ('Bob', 40), ('Charlie', 75), ('David', 49)]

```

---

## 🔹 Task 3: Add a New Student

**Objective:** Use `append()` to add one more student and score.

```python
# Add a new student
names.append("Eve")
scores.append(90)

# Recreate the updated pairings
student_pairs = list(zip(names, scores))
print("Updated Student Pairs:", student_pairs)

Updated Student Pairs: [('Alice', 65), ('Bob', 40), ('Charlie', 75), ('David', 49), ('Eve', 90)]

```

---

## 🔹 Task 4: Mark Pass or Fail

**Objective:** Use `map()` and a lambda function to evaluate who passed.

```python
# Determine pass/fail for each score
passed_status = list(map(lambda score: score >= 50, scores))
print("Passed Status:", passed_status)

Passed Status: [True, False, True, False]

```

---

## 🔹 Task 5: Build Student Dictionary

**Objective:** Combine names, scores, and pass status into a dictionary.

```python
# Build a dictionary with all student info
student_dict = {
    name: {"score": score, "passed": passed}
    for name, score, passed in zip(names, scores, passed_status)
}

print("Student Dictionary:")
for student, info in student_dict.items():
    print(f"{student}: {info}")

Student Dictionary:
Alice: {'score': 65, 'passed': True}
Bob: {'score': 40, 'passed': False}
Charlie: {'score': 75, 'passed': True}
David: {'score': 49, 'passed': False}
```

---

## 🔹 Task 6: Extract Passed Students as a Set

**Objective:** Use a `set` to collect students who passed.

```python
# Extract names of students who passed
passed_students = {name for name, info in student_dict.items() if info["passed"]}
print("Passed Students:", passed_students)
Passed Students: {'Charlie', 'Alice'}

```

---

## 🔹 Task 7: Numbered List with `enumerate()`

**Objective:** Use `enumerate()` to list all students with index numbers.

```python
# Print numbered list of all students
print("All Students:")
for i, name in enumerate(names, start=1):
    print(f"{i}. {name}")

All Students:
1. Alice
2. Bob
3. Charlie
4. David
```

---

## ✅ Summary of Python Concepts Covered

| Function/Concept | Task(s) Used In | Purpose |
|------------------|-----------------|---------|
| `split()`        | Task 1          | Splits strings into lists |
| `strip()`        | Task 1          | Removes whitespace |
| `zip()`          | Tasks 2, 5      | Pairs items from multiple iterables |
| `append()`       | Task 3          | Adds item to list |
| `map()`          | Task 4          | Applies function to list |
| `lambda`         | Task 4          | Anonymous inline function |
| `dict`           | Task 5          | Stores structured data |
| `set`            | Task 6          | Holds unique passed students |
| `enumerate()`    | Task 7          | Adds indices to iteration |
