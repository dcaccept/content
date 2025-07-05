# ✅ Ansible Scenario-Based Questions (Production & Real-World)

## 1️⃣ Rolling out a configuration change

**Question:**  
You are asked to update an NTP configuration across 500 servers using Ansible. How would you approach this task?

**What to listen for:**
- Use inventory grouping to target hosts safely
- Validate current state (gather facts)
- Create idempotent playbook (ensures repeated runs don't break things)
- Test on a small batch first
- Implement dry run (`--check`)
- Use serial or batch mode for gradual rollout
- Validate post-change (e.g., via handlers or verifying status)
- Have rollback strategy (e.g., revert previous config)

---

## 2️⃣ Handling host failure during playbook execution

**Question:**  
If a playbook fails on some hosts midway, how would you handle it?

**What to listen for:**
- Understand `--limit` and `--start-at-task` to resume
- Use `serial` keyword to limit blast radius
- Implement handlers for cleanup or revert
- Check `failed_when` and `ignore_errors` usage carefully
- Debug logs and facts to analyze failure
- Correct issue and re-run targeted only on failed hosts

---

## 3️⃣ Managing secrets securely

**Question:**  
How do you handle sensitive data (like passwords or API keys) in your Ansible workflows?

**What to listen for:**
- Use `ansible-vault` to encrypt secrets
- Avoid plaintext vars and hardcoded values
- Store vault passwords securely (e.g., CI/CD vault plugins)
- Pass vault password via prompt or environment variable
- Use Ansible Tower or AWX credentials feature if applicable

---

## 4️⃣ Deploying a new application stack

**Question:**  
You need to deploy a new multi-tier application using Ansible. What steps would you follow?

**What to listen for:**
- Collect application and infra requirements
- Define clear roles for each layer (DB, backend, frontend, LB, etc.)
- Use reusable roles and group_vars
- Validate infra (check pre-requisites)
- Test on staging environment first
- Use `tags` to control partial deployments
- Plan rollout strategy, include rollback
- Document each step and maintain playbooks in version control

---

## 5️⃣ Unexpected downtime after Ansible deployment

**Question:**  
After running an Ansible deployment, some services went down unexpectedly. How would you troubleshoot?

**What to listen for:**
- Check Ansible logs and detailed output
- Verify changes (diff) in configs
- Look at service status on affected hosts
- Use `ansible` ad-hoc commands to quickly check hosts
- Rollback or re-run with corrected playbook
- Add additional checks and handlers to future playbooks to avoid recurrence

---

### A. Dealing with slow hosts

**Question:**  
What if certain hosts are very slow during execution and cause the entire playbook to delay?

**Expected:**
- Use `forks` to parallelize
- Use `serial` or `throttle` to break into smaller batches
- Identify and fix performance bottlenecks on slow hosts
- Separate slow hosts into a different group if needed

---

### B. Ansible version compatibility

**Question:**  
If your playbook works fine in your environment but fails in another due to Ansible version differences, how would you handle it?

**Expected:**
- Check compatibility matrix
- Explicitly specify minimum Ansible version in playbooks (`min_ansible_version`)
- Use version-specific syntax carefully
- Recommend standardized version or containerized execution

---

### C. Idempotency assurance

**Question:**  
How do you ensure your Ansible playbooks are idempotent?

**Expected:**
- Avoid shell/command tasks unless necessary
- Use Ansible modules (e.g., `copy`, `template`, `package`) with proper states
- Validate repeatedly in dev/staging
- Check Ansible output: no "changed" status if no real change

---

