🐍 Python requests — Handling Response Types
🔥 Introduction
When you make a GET request using Python’s requests library, the server returns a response object. The content type of this response can vary:

Plain text (e.g., HTML, text files)

JSON (structured data)

Binary (images, PDFs, etc.)

You must decide how to read the response based on what the server sends.

💡 How to choose how to read the response
✅ response.text
Returns content as string (decoded from bytes).

Use when the response is text-based (HTML, plain text, XML).

python
Copy
Edit
import requests

r = requests.get("https://www.example.com")
print(r.text)  # String representation of the HTML page
✅ response.json()
Parses the content as JSON, and returns a Python dictionary (or list, depending on JSON structure).

Use when the server returns JSON, and header Content-Type is application/json.

python
Copy
Edit
import requests

r = requests.get("https://api.github.com/repos/python/cpython")
data = r.json()
print(data["full_name"])
✅ response.content
Returns raw bytes (not decoded).

Use for binary files like images, PDFs, audio files, etc.

python
Copy
Edit
r = requests.get("https://example.com/logo.png")
with open("logo.png", "wb") as f:
    f.write(r.content)
🟢 How to "ask" for a specific response type
You can suggest the type of data you want by adding an Accept header to your request.

python
Copy
Edit
headers = {"Accept": "application/json"}
r = requests.get("https://api.example.com/data", headers=headers)
Common Accept header values
Value	Meaning
application/json	Ask for JSON data
text/html	Ask for HTML page
text/plain	Ask for plain text
application/xml	Ask for XML data

⚠️ Important: The server is not forced to return this type — it will try to honor your request, but ultimately decides what to send.

💬 Check Content Type
To verify what you actually received:

python
Copy
Edit
print(r.headers["Content-Type"])
This helps you decide whether to use .json(), .text, or .content.

✅ Summary Table
What you expect	What to do	How to read it
JSON data	Set Accept: application/json header (optional)	Use .json()
HTML or plain text	Set Accept: text/html or text/plain header (optional)	Use .text
Binary data	Usually no need to set header	Use .content

📝 Quiz: Test Your Understanding
❓ Questions
1️⃣ Which method should you use if the server returns a JSON response?
2️⃣ How can you suggest to the server that you want JSON data?
3️⃣ What happens if you call .json() on an HTML response?
4️⃣ How do you check what content type the server returned?
5️⃣ Which attribute should you use if you want raw binary bytes?

✅ Answers
1️⃣ response.json()

2️⃣ By setting the Accept header to application/json in your request.

3️⃣ It will raise a JSONDecodeError because HTML is not valid JSON.

4️⃣ By checking response.headers["Content-Type"].

5️⃣ response.content.

🌟 Final Takeaway
You can ask for a preferred format using Accept.

You can choose how to process the response in Python: .json(), .text, or .content.

Always check the Content-Type header to confirm what the server actually returned.
