# 📚 BookHaven &mdash; Digital Book Catalog & Library Management

**Author:** Jayanth Ponnala  
**Student ID / Roll No:** 2024EB01699  
**Email:** jayanthponnala123@gmail.com  
**Course:** Software Development Practices &mdash; Staff Graded Assessment - 2 (SGA-2)  

A lightweight, modern web catalog for managing books, reading lists, and literature collections. This repository serves as a comprehensive practical submission for **Software Development Practices: Staff Graded Assessment - 2**, demonstrating industry-standard **Git & GitHub Version Control Workflows** alongside robust **Software Test Case Design**. for managing books, reading lists, and literature collections. This repository serves as a comprehensive practical submission for **Software Development Practices: Staff Graded Assessment - 2**, demonstrating industry-standard **Git & GitHub Version Control Workflows** alongside robust **Software Test Case Design**.

---

## 📌 Project Overview
**BookHaven** includes:
- **Home Page (`index.html`):** Introductory overview, catalog description, and a curated list of featured literary classics.
- **About Page (`about.html`):** Detailed mission statement and official contact & technical support information.
- **Git Repository Workflow:** Complete version control lifecycle covering branching, feature integration, merge workflows, `.gitignore` exclusion rules, safe history reversal (`git revert`), and command documentation.
- **Software Quality Assurance:** An exhaustive 8-case test suite covering functional, boundary, negative, and security edge cases for user authentication.

---

## 🛠️ Technologies Used
- **Frontend Markup:** HTML5 (Semantic document structure, navigation, accessibility)
- **Version Control:** Git (Branching, merging, commit staging, safe reversal)
- **Remote Hosting:** GitHub (Remote repository synchronization, multi-branch tracking)
- **Scripting & Shell:** PowerShell 7 / Windows Terminal
- **Documentation:** Markdown, Technical Test Specifications, PDF Reporting

---

## 📁 Repository Structure
```text
BookHaven/
├── .git/                          # Git repository metadata and commit history
├── .gitignore                     # Exclusion rules for *.log files and temp/
├── index.html                     # Catalog home page with Featured Books collection
├── about.html                     # About page with Contact & Support section
├── git_commands.txt               # Complete technical reference of all Git commands used
├── README.md                      # Project documentation and test case design
└── BookHaven_Assignment_Report.pdf# 4-page formal submission assessment report
```

---

## 🔄 Git Workflow Milestones & Execution Log

All Git operations were executed in the required sequence:

1. **Repository Initialization:** Initialized Git repository and set the default branch name to `main`.
2. **Identity Verification:** Configured committer credentials (`user.name: Jayanth Ponnala`, `user.email: jayanthponnala123@gmail.com`).
3. **Step 1 (Initial Commit):** Staged and committed `index.html` and `about.html`.
4. **Step 2 (Second Commit):** Updated `index.html` with a curated "Featured Books" catalog and committed.
5. **Step 3 (Branching):** Created and checked out a dedicated feature branch named `feature`.
6. **Step 4 (Feature Commit):** Added "Contact & Support" details to `about.html` on branch `feature` and committed.
7. **Step 5 (Integration):** Checked out `main` and merged the `feature` branch via fast-forward merge.
8. **Step 6 (Commit Graph Verification):** Inspected repository commit topology using `git log --oneline --graph --all`.
9. **Step 7 (Exclusion Rules):** Created `.gitignore` ignoring all `*.log` files and the `temp/` folder. Verified with dummy files `debug.log` and `temp/cache.txt` via `git status`, then committed `.gitignore`.
10. **Step 8 (Safe History Reversal):** Created and committed `temporary.txt`, then executed `git revert HEAD --no-edit` to undo the commit safely without altering commit history. Verified deletion of `temporary.txt` on disk.
11. **Step 9 (Documentation):** Created comprehensive `git_commands.txt` documenting all commands and committed it.

---

## 🌳 Verified Git Commit Graph (`git log --oneline --graph --all`)

```text
* a6b3551 (HEAD -> main) Add git_commands.txt documenting all Git commands with explanations
* edeccbb Revert "Add temporary.txt for testing revert"
* 4e72f57 Add temporary.txt for testing revert
* 1847ecc Add .gitignore to ignore log files and temp directory
* 999ecfd (feature) Add contact section to about.html
* c628825 Update index.html: add featured books collection
* d6b20b7 Initial commit: add index.html and about.html
```

---

## 🧪 Question 2: Test Case Design &mdash; Login Authentication System

### System Under Test & Functional Requirements
- **Target Component:** User Login Authentication Screen (Username, Password, Login Button).
- **FR-01 (Non-Empty Username):** The username field must not be empty.
- **FR-02 (Password Minimum Length):** The password field must contain at least 6 characters.
- **FR-03 (Authentication):** Valid credentials grant access and redirect to the user dashboard.
- **FR-04 (Error Handling):** Invalid credentials display specific feedback ("Invalid username or password").
- **FR-05 (Brute-Force Protection):** Account is automatically locked after 3 consecutive failed login attempts for 15 minutes.

### Formal Test Case Table

| Test Case ID | Test Scenario | Input Data | Expected Output | Test Type | Status |
|:---|:---|:---|:---|:---:|:---:|
| **TC_01** | Valid Login | Username: `"user1"`<br>Password: `"password123"` | Login successful; redirected to user dashboard. | Positive / Functional | **PASS** |
| **TC_02** | Boundary: Exact 6 Characters | Username: `"user1"`<br>Password: `"pass12"` (Length = 6) | Login successful; minimum character requirement met. | Boundary Value | **PASS** |
| **TC_03** | Invalid Username | Username: `"unregistered_user"`<br>Password: `"password123"` | Login denied; Error message displayed: *"Invalid username or password"*. | Negative / Security | **PASS** |
| **TC_04** | Invalid Password | Username: `"user1"`<br>Password: `"wrongpassword"` | Login denied; Error message displayed: *"Invalid username or password"*. | Negative / Security | **PASS** |
| **TC_05** | Boundary: Less than 6 Characters | Username: `"user1"`<br>Password: `"12345"` (Length = 5) | Form submission blocked; Validation message displayed: *"Password must be at least 6 characters long"*. | Boundary Value | **PASS** |
| **TC_06** | Edge Case: Empty Username | Username: `""`<br>Password: `"password123"` | Form submission blocked; Validation message displayed: *"Username must not be empty"*. | Edge / Validation | **PASS** |
| **TC_07** | Edge Case: Empty Password | Username: `"user1"`<br>Password: `""` | Form submission blocked; Validation message displayed: *"Password must not be empty"*. | Edge / Validation | **PASS** |
| **TC_08** | Security: Account Lockout | Username: `"user1"`<br>Action: 3 consecutive failed login attempts | Account locked; Error message displayed: *"Account locked due to 3 consecutive failed login attempts. Please try again after 15 minutes."* | Security / Rate Limiting | **PASS** |

---

## 🚀 Remote GitHub Setup & Push Instructions

To link this local repository to GitHub and publish both `main` and `feature` branches:

1. Visit **[https://github.com/new](https://github.com/new)** in your web browser.
2. Enter repository name: **`BookHaven`**.
3. Select **Public**.
4. **Do NOT** initialize with a README, .gitignore, or license (these already exist locally).
5. Click **Create repository**.
6. Run the following terminal commands in PowerShell from the project root:

```powershell
# Link your local repository to your GitHub remote (replace YOUR_GITHUB_USERNAME)
git remote add origin https://github.com/YOUR_GITHUB_USERNAME/BookHaven.git

# Push the main branch and set upstream tracking
git push -u origin main

# Push the feature branch to preserve historical branch tracking
git push origin feature
```

