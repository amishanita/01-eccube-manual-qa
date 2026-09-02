# GitHub Setup Guide

**How to push this project to GitHub and share with recruiters**

---

## STEP 1: Create GitHub Account (If You Don't Have One)

1. Go to https://github.com
2. Click "Sign up"
3. Follow the steps (email, password, username)
4. Verify your email
5. You now have a GitHub account

---

## STEP 2: Create a New Repository on GitHub

1. Log in to GitHub
2. Click the **+** icon in top-right corner
3. Select **New repository**
4. Fill in:

| Field | Value |
|---|---|
| Repository name | `01-eccube-manual-qa` |
| Description | `Manual QA Portfolio - EC-CUBE 4.2.3 Testing Project` |
| Public/Private | **PUBLIC** ✓ |
| Initialize with README | **NO** (we have our own) |

5. Click **Create repository**

**Result:** You now have an empty GitHub repo at:
```
https://github.com/[your-username]/01-eccube-manual-qa
```

---

## STEP 3: Copy This Project Folder to Your Computer

1. Download `01-eccube-manual-qa.zip` from outputs folder
2. Extract it to your computer (any location)
3. You should see:
```
01-eccube-manual-qa/
├── README.md
├── PROJECT-COMPLETION-SUMMARY.md
├── GITHUB-SETUP.md (this file)
├── .gitignore
├── docs/
├── test-cases/
├── evidence/
├── excel/
├── jira/
└── [other folders]
```

---

## STEP 4: Open Terminal/Command Prompt

**On Mac:**
- Open Applications → Utilities → Terminal

**On Windows:**
- Search for "Command Prompt" or "PowerShell"

**On Linux:**
- Open Terminal

---

## STEP 5: Navigate to the Project Folder

Type this command (replace `/path/to/` with your actual path):

```bash
cd /path/to/01-eccube-manual-qa
```

**Example on Mac:**
```bash
cd ~/Downloads/01-eccube-manual-qa
```

**Example on Windows:**
```bash
cd C:\Users\YourName\Downloads\01-eccube-manual-qa
```

---

## STEP 6: Initialize Git in This Folder

```bash
git init
```

**Result:** A `.git` folder is created (hidden)

---

## STEP 7: Add All Files to Git

```bash
git add .
```

**Result:** All files are staged for commit

---

## STEP 8: Create First Commit

```bash
git commit -m "Initial commit: EC-CUBE Manual QA Portfolio"
```

**Result:** All files are committed

---

## STEP 9: Add GitHub as Remote

Replace `[your-username]` with your actual GitHub username:

```bash
git remote add origin https://github.com/[your-username]/01-eccube-manual-qa.git
```

**Example:**
```bash
git remote add origin https://github.com/john-smith/01-eccube-manual-qa.git
```

---

## STEP 10: Rename Branch (If Needed)

GitHub uses "main" as default. Check your branch:

```bash
git branch
```

If it says "master", rename it:

```bash
git branch -M main
```

---

## STEP 11: Push to GitHub

```bash
git push -u origin main
```

**The first time, GitHub might ask for your credentials:**
- Username: Your GitHub username
- Password: Your GitHub token (not your password)

**To create a GitHub token:**
1. Go to https://github.com/settings/tokens
2. Click "Generate new token"
3. Name it "git-push-token"
4. Select scopes: `repo`
5. Click "Generate token"
6. Copy the token (you won't see it again)
7. Use this token as your password when pushing

---

## STEP 12: Verify on GitHub

1. Go to https://github.com/[your-username]/01-eccube-manual-qa
2. You should see all your files displayed
3. README.md should be visible at the bottom

---

## STEP 13: Get Your GitHub Link

Your project is now at:

```
https://github.com/[your-username]/01-eccube-manual-qa
```

**Share this link with recruiters!**

---

## STEP 14: Update README on GitHub (Optional)

If you want to customize the README just for GitHub:

1. Go to your repo on GitHub
2. Click on `README.md`
3. Click the pencil icon (Edit)
4. Add this at the very top:

```markdown
# EC-CUBE Manual QA Portfolio

**QA Test Design Project for EC-CUBE 4.2.3**

🔗 **Download Full Project:** [01-eccube-manual-qa.zip](https://github.com/[your-username]/01-eccube-manual-qa/releases/download/v1.0/01-eccube-manual-qa.zip)

📋 **Project Summary:**
- 40 test cases designed
- 27 requirements mapped
- 20 test scenarios
- 4 real mobile screenshots
- Complete QA documentation
- AI-assisted design (transparent disclosure)

👤 **Applying for:** Junior QA Engineer roles in Japan

📖 **Start here:** Read [PROJECT-COMPLETION-SUMMARY.md](PROJECT-COMPLETION-SUMMARY.md) for full details.
```

5. Click "Commit changes"

---

## QUICK REFERENCE — Git Commands

```bash
# First time only
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/[username]/01-eccube-manual-qa.git
git branch -M main
git push -u origin main

# After making changes
git add .
git commit -m "Description of changes"
git push
```

---

## EMAIL TEMPLATE FOR RECRUITERS (With GitHub Link)

```
Subject: Manual QA Portfolio - EC-CUBE Testing Project

Dear [Recruiter Name],

I'm sharing my manual QA portfolio project for the EC-CUBE 4.2.3 
e-commerce platform. This project demonstrates my test design, 
requirements analysis, and traceability skills.

**GitHub Repository:**
https://github.com/[your-username]/01-eccube-manual-qa

**Project Highlights:**
• 40 professionally designed test cases
• 27 functional requirements with full traceability
• 20 test scenarios
• 4 real mobile testing screenshots
• 8 comprehensive documentation files
• 6 Excel workbooks with formulas

**Approach:**
This is an AI-assisted portfolio where I performed hands-on 
observation and all test design decisions. The project includes 
real evidence from actual application testing.

I'm interested in QA Engineer positions in Japan and welcome 
feedback on this work.

Best regards,
[Your Name]
[Your Email]
[Your Phone]
```

---

## TROUBLESHOOTING

**Problem: "fatal: not a git repository"**
- Solution: Make sure you're in the correct folder (use `pwd` to check)

**Problem: "remote origin already exists"**
- Solution: Remove it first: `git remote remove origin`
- Then add it again: `git remote add origin https://...`

**Problem: "Permission denied (publickey)"**
- Solution: You need to set up SSH keys or use a GitHub token instead

**Problem: Can't push to GitHub**
- Solution: Use GitHub token instead of password (see Step 11)

---

## AFTER PUSHING TO GITHUB

### Share the Link:
```
https://github.com/[your-username]/01-eccube-manual-qa
```

### Track Views (Optional):
1. Go to your repo
2. Click "Insights" tab
3. You can see who viewed your project

### Keep It Updated:
- If you make changes, use: `git add . && git commit -m "message" && git push`
- GitHub will show your work history

---

## WHAT RECRUITERS WILL SEE

When they visit your GitHub repo:

1. **Folder structure** — All 53 files organized professionally
2. **README.md** — Project overview (first thing they see)
3. **PROJECT-COMPLETION-SUMMARY.md** — Full guide (they'll read this)
4. **docs/** — All documentation
5. **evidence/** — Screenshots folder with 4 images
6. **excel/** — All workbooks
7. **test-cases/** — All test designs
8. **Git history** — Shows you pushed it (proves it's real)

---

**You're done! Your project is now on GitHub, ready to share with recruiters.**

Good luck! 頑張ってください！
