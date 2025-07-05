# ✅ API & REST API Scenario-Based Questions (Production & Real-World)

## 1️⃣ Designing a new API endpoint

**Question:**  
Imagine you’re designing an API endpoint to update user details. What HTTP method would you use, and what status codes would you return on success or failure?

**What to listen for:**
- Use `PUT` or `PATCH` for update (PATCH for partial updates)
- Status codes: 
  - 200 OK (success with response)
  - 204 No Content (success without response)
  - 400 Bad Request (invalid input)
  - 404 Not Found (user not found)
  - 500 Internal Server Error (unexpected failure)

---

## 2️⃣ Authentication vs Authorization

**Question:**  
What is the difference between authentication and authorization? How do you implement both in an API?

**What to listen for:**
- Authentication: verifying identity (e.g., login, tokens)
- Authorization: permission to access resources (roles, scopes)
- Implementation:
  - Authentication: JWT, OAuth2, API keys
  - Authorization: role-based access control (RBAC), scopes

---

## 3️⃣ Securing an API

**Question:**  
If your API is exposed publicly, what measures would you take to secure it?

**What to listen for:**
- Use HTTPS everywhere
- Use authentication and authorization
- Validate input and output (avoid injections)
- Rate limiting and throttling
- Use API gateway or reverse proxy
- Logging and monitoring suspicious activity

---

## 4️⃣ Versioning an API

**Question:**  
How would you handle backward compatibility when releasing a new version of your API?

**What to listen for:**
- Introduce versioning (e.g., `/v1/`, `/v2/`)
- Deprecate old endpoints gradually
- Document changes clearly
- Support old clients until migration

---

## 5️⃣ Handling long-running requests

**Question:**  
Your API needs to handle a large file upload and processing job. How would you design it?

**What to listen for:**
- Return 202 Accepted and provide job ID
- Client polls or subscribes to status endpoint
- Use background processing (queue, worker)
- Provide final download link or status

---

## 6️⃣ Rate limiting scenario

**Question:**  
How would you handle excessive requests from a single client?

**What to listen for:**
- Implement rate limiting (e.g., per IP or API key)
- Use HTTP status 429 Too Many Requests
- Add Retry-After header
- Optionally block or ban abusive clients

---

## 7️⃣ Using query parameters vs body

**Question:**  
When would you pass data in query parameters vs request body in an API?

**What to listen for:**
- Query parameters: for filtering, sorting, pagination, non-sensitive data
- Body: for creating or updating resources (complex or sensitive data)

---

## 8️⃣ API testing

**Question:**  
How would you test your API to ensure it works as expected?

**What to listen for:**
- Unit tests for logic
- Integration tests (endpoints + DB)
- Contract tests (schemas, response shape)
- Load/stress tests
- Use tools: Postman, curl, pytest, Swagger, etc.

---

## 9️⃣ Error handling and reporting

**Question:**  
How should your API respond to unexpected errors?

**What to listen for:**
- Proper status codes (e.g., 500 for internal errors)
- Clear error message (but avoid leaking internal details)
- Unique error codes for tracking
- Log error details internally

---

## 🔎 Bonus: Regex & extraction task

**Question:**  
Given this sample text from a network device:

