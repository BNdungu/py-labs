# Git & GitHub Workflow Guide

This is your step-by-step guide for submitting tasks using Git and GitHub.
Follow this every time you work on a new task.

---

## One-Time Setup (do this only once)

### 1. Fork the repo
- Go to the main GitHub repo
- Click the **Fork** button (top right)
- This creates your own copy of the repo under your GitHub account

### 2. Clone your fork to your computer
```bash
git clone https://github.com/YOUR-USERNAME/python-tasks.git
cd python-tasks
```

### 3. Set the main repo as "upstream" (so you can get new tasks later)
```bash
git remote add upstream https://github.com/REPO-OWNER/python-tasks.git
```

---

## Every Task — Step by Step

### Step 1: Get the latest tasks
```bash
git fetch upstream
git merge upstream/master
```

### Step 2: Create a new branch for your task
Always work on a new branch — never work directly on `master`.
```bash
git checkout -b task-01
```
Name the branch after the task, e.g. `task-01`, `task-02`, etc.

### Step 3: Open the task folder
Go into `tasks/task_01_variables_and_input/` and read the `README.md` first.
Then write your code in `solution.py`.

### Step 4: Save your work with Git

Check what files you changed:
```bash
git status
```

Stage your solution file:
```bash
git add tasks/task_01_variables_and_input/solution.py
```

Commit with a clear message:
```bash
git commit -m "task 01: variables and input solution"
```

### Step 5: Push your branch to GitHub
```bash
git push origin task-01
```

### Step 6: Open a Pull Request
- Go to your fork on GitHub
- You'll see a yellow banner saying **"Compare & pull request"** — click it
- Set the base repo to the main repo, base branch `master`
- Title it clearly: `Task 01 - Variables and Input`
- Click **Create Pull Request**

Your code will be reviewed and comments left. If changes are needed,
edit your `solution.py`, then run:
```bash
git add tasks/task_01_variables_and_input/solution.py
git commit -m "task 01: fix after review"
git push origin task-01
```
The PR updates automatically.

---

## Key Git Commands — Quick Reference

| Command | What it does |
|---|---|
| `git status` | Show what files have changed |
| `git add <file>` | Stage a file for commit |
| `git commit -m "message"` | Save a snapshot with a message |
| `git push origin <branch>` | Upload your branch to GitHub |
| `git checkout -b <name>` | Create and switch to a new branch |
| `git fetch upstream` | Download new tasks from upstream |
| `git merge upstream/master` | Apply upstream updates to your copy |
| `git log --oneline` | See your commit history |

---

## Rules

- Never edit files outside your `tasks/` folder
- One branch per task
- Write a meaningful commit message — not just "done" or "fix"
- Open a PR when you're ready for review, not before
