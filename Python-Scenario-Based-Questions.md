# ✅ Python Scenario-Based Questions (Production & Real-World)

## 1️⃣ Requirement to extract data

**Question:**  
You received a requirement to extract specific data (e.g., IP addresses, software versions, or error codes) from certain tools or log outputs. What details would you first ask for, and how would you approach designing and implementing this extraction in Python?

**What to listen for:**
- Clarify requirement first (exact data needed, format, source of data)
- Check data source (file, API, database, logs)
- Understand frequency and volume
- Choose parsing tools: regex, string methods, or libraries like `json`, `xml`, etc.
- Write modular code with functions
- Add error handling and validation
- Test on sample data
- Document assumptions and edge cases

---

## 2️⃣ Automation script failing in production

**Question:**  
There is an existing automation script running in production, and it suddenly started throwing errors. How would you troubleshoot this situation?

**What to listen for:**
- Check logs and traceback details
- Identify recent changes (code, environment, dependencies)
- Validate input data correctness
- Isolate components/modules to narrow down problem
- Add debug logs if necessary
- Test in a dev or staging environment first
- Fix root cause (not just quick patch)
- After fix: test, redeploy, monitor, update documentation

---

## 3️⃣ Deploying a critical Python script

**Question:**  
You’ve developed a Python script to automate a critical task. How would you prepare, test, and deploy this script in a production environment?

**What to listen for:**
- Write proper unit and integration tests
- Validate with test data
- Use version control (Git) and review code
- Package dependencies properly (requirements.txt, virtualenv, container)
- Peer review or code review
- Deploy to staging first
- Monitor logs and system after deployment
- Rollback plan if failure happens
- Documentation and communication with stakeholders

---

## 4️⃣ Deploying a new feature in production

**Question:**  
Imagine you’re working in production and receive a request to deploy a newly developed feature. Can you walk me through the steps you would take from receiving the request to the feature being live in production?

**What to listen for:**
- Understand and clarify business requirements first
- Design and implement (code)
- Write/extend tests
- Peer review
- Merge and push to version control
- Deploy to staging, validate with test cases
- Obtain sign-off or approval
- Deploy to production in controlled manner
- Monitor closely, check logs, rollback plan
- Communicate release notes and update docs



### A. Upstream data format change

**Question:**  
What if the data extraction logic suddenly stops working because the upstream data format changed? How would you handle this?

**Expected:**
- Check diff in upstream format
- Update parsing logic or regex
- Add format version checks if possible
- Create tests for new and old formats
- Plan a controlled rollout

---

### B. Handling API rate limits

**Question:**  
If your Python script interacts with APIs and starts hitting rate limits, what would you do?

**Expected:**
- Respect rate limit headers (e.g., Retry-After)
- Add exponential backoff
- Implement local caching
- Optimize calls (reduce redundant requests)

---

### C. Ensuring code security before deployment

**Question:**  
How do you ensure your Python code is secure before deploying to production?

**Expected:**
- Avoid hardcoded secrets, use vault or environment variables
- Validate all inputs
- Use logging carefully (no sensitive data)
- Use static analysis tools (e.g., Bandit)
- Follow least-privilege principles


