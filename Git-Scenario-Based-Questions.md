# ✅ Git Scenario-Based Questions (Production & Real-World)

## 1️⃣ Feature development workflow

**Question:**  
If you're developing a new feature in a large shared repository, what steps would you take before merging your work?

**What to listen for:**
- Create a new feature branch
- Regularly pull/rebase from main to avoid drift
- Write clear commits (atomic, meaningful messages)
- Add or update tests
- Open a pull/merge request for review
- Use CI checks before merging
- Squash commits if needed for cleaner history

---

## 2️⃣ Resolving merge conflicts

**Question:**  
You tried to merge your feature branch into main and encountered conflicts. How would you resolve them?

**What to listen for:**
- Run `git status` to see conflicting files
- Open conflicted files and fix manually
- Use `git add` to mark resolved
- Run `git commit` to complete merge
- Test thoroughly after resolving
- Push updated branch and update PR

---

## 3️⃣ Accidentally pushed secrets

**Question:**  
You accidentally pushed a secret key to a public repository. What steps would you take?

**What to listen for:**
- Immediately revoke or rotate the key
- Remove the secret from history (`git filter-branch` or `git filter-repo`)
- Force push updated history
- Notify impacted teams
- Add secret scanning hooks or tools to avoid future incidents

---

## 4️⃣ Reverting a bad deployment

**Question:**  
A recent commit caused a production issue. How would you revert it using Git?

**What to listen for:**
- Identify problematic commit (via `git log` or `git blame`)
- Use `git revert <commit>` to create a new reversal commit (safe approach)
- Test changes locally or on staging
- Push revert commit and deploy
- If necessary, hotfix with further adjustments

---

## 5️⃣ Cleaning up commit history

**Question:**  
Your branch has messy commit history with many "fix" commits. How would you clean it up before merging?

**What to listen for:**
- Use `git rebase -i` (interactive rebase) to squash or reorder commits
- Group related changes
- Rewrite commit messages clearly
- Force push updated branch (after confirming no shared work)

---

## 6️⃣ Undoing a local commit

**Question:**  
How do you undo your last local commit but keep your changes unstaged?

**What to listen for:**
- Use `git reset --soft HEAD~1` to undo last commit but keep changes staged
- Or `git reset --mixed HEAD~1` to keep changes unstaged

---

## 7️⃣ Tagging and releases

**Question:**  
How do you create a release tag in Git? Why is it useful?

**What to listen for:**
- Use `git tag v1.0.0` or `git tag -a v1.0.0 -m "Release 1.0.0"`
- Push tags (`git push origin v1.0.0`)
- Tags mark specific points (e.g., releases), easier rollback, traceability

---

## 8️⃣ Bisecting a bug

**Question:**  
There’s a bug introduced somewhere in the last 50 commits. How would you identify which commit caused it?

**What to listen for:**
- Use `git bisect start`
- Mark bad (current buggy) and good (last known working) commits
- Git auto-checks commits in between
- Test after each checkout, mark as good or bad, repeat
- Git eventually pinpoints problematic commit

---

### A. Git hooks

**Question:**  
How would you enforce commit message style in your team?

**Expected:**
- Use client-side `commit-msg` hook
