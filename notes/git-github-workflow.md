# Git & GitHub Workflow Guide

This guide is written for someone using Git for the very first time.
Read it from top to bottom before you do anything else.

---

## What is Git?

Git is a tool that tracks changes to your code over time. Think of it like
"save points" in a video game — every time you commit, you save a snapshot
of your work. If you break something, you can always go back.

Git works **on your computer** (locally).

## What is GitHub?

GitHub is a website that stores your Git projects online. It lets you:
- Back up your code in the cloud
- Share your code with others
- Submit your work for review

Git is the tool. GitHub is the website that hosts your work.

---

## Helpful Resources (read/bookmark these)

| Resource | What it covers |
|---|---|
| [GitHub Skills](https://skills.github.com/) | Free interactive GitHub courses — start with "Introduction to GitHub" |
| [Learn Git Branching](https://learngitbranching.js.org/) | Visual, interactive game that teaches Git step by step |
| [Git official docs](https://git-scm.com/doc) | Reference for every Git command |
| [GitHub Docs — Getting Started](https://docs.github.com/en/get-started) | GitHub's own beginner guide |
| [Oh My Git!](https://ohmygit.org/) | A game for learning Git visually |

Start with **GitHub Skills** and **Learn Git Branching** — they are the most
beginner-friendly.

---

## Part 1 — Install and Set Up Git

### Install Git
- **Windows**: Download from https://git-scm.com/download/win and run the installer
- **Mac**: Open Terminal and run `git --version` — if not installed, it will prompt you
- **Linux**: Run `sudo apt install git`

Check it worked:
```bash
git --version
```
You should see something like `git version 2.x.x`.

### Tell Git who you are
Git needs your name and email to label your commits. Run these two commands
once — you only need to do this once per computer:

```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

Use the same email you signed up to GitHub with.

Confirm it saved:
```bash
git config --list
```

---

## Part 2 — Create a GitHub Account

1. Go to https://github.com
2. Click **Sign up** and follow the steps
3. Verify your email address
4. You now have a GitHub account

---

## Part 3 — One-Time Setup for This Repo

You only do this once at the start.

### Step 1: Fork the repo

Forking means making your own personal copy of the repo on GitHub.

1. Go to the main repo on GitHub
2. Click the **Fork** button in the top-right corner
3. Click **Create fork**
4. You now have your own copy at `https://github.com/YOUR-USERNAME/python-tasks`

### Step 2: Clone your fork to your computer

Cloning means downloading the repo from GitHub to your computer so you can
work on it locally.

Open your terminal (or Git Bash on Windows), navigate to where you want the
folder, then run:

```bash
git clone https://github.com/YOUR-USERNAME/python-tasks.git
```

This creates a folder called `python-tasks` on your computer. Move into it:

```bash
cd python-tasks
```

All Git commands from now on must be run inside this folder.

### Step 3: Connect to the main repo (upstream)

Your clone is connected to your fork, but not to the main repo. Add that
connection so you can pull down new tasks when they are added:

```bash
git remote add upstream https://github.com/REPO-OWNER/python-tasks.git
```

Check your connections:
```bash
git remote -v
```

You should see two remotes:
- `origin` — your fork (you push to this)
- `upstream` — the main repo (you only pull from this)

---

## Part 4 — Every Task, Step by Step

Repeat these steps for every task.

---

### Step 1: Get the latest tasks

Before starting any task, make sure you have the latest version:

```bash
git fetch upstream
git merge upstream/master
```

- `git fetch upstream` — downloads any new tasks from the main repo
- `git merge upstream/master` — applies those changes to your local copy

---

### Step 2: Create a branch for this task

A branch is a separate workspace. You always work on a branch — never
directly on `master`. This keeps your work organised and separate.

```bash
git checkout -b task-01
```

What this does:
- Creates a new branch called `task-01`
- Switches you to that branch automatically

You should name the branch after the task: `task-01`, `task-02`, etc.

Check which branch you are on at any time:
```bash
git branch
```
The branch with a `*` next to it is your current branch.

---

### Step 3: Do the task

1. Open the task folder, e.g. `tasks/task_01_variables_and_input/`
2. Read `README.md` carefully — it has the instructions
3. Write your code in `solution.py`

---

### Step 4: Check what you changed

Before saving anything, see what Git noticed:

```bash
git status
```

This shows:
- **Red** files = changed but not yet staged (not ready to commit)
- **Green** files = staged (ready to commit)

---

### Step 5: Stage your file

Staging means telling Git "I want to include this file in my next save point."

```bash
git add tasks/task_01_variables_and_input/solution.py
```

Run `git status` again — your file should now be green.

You can also stage everything changed in one go (use carefully):
```bash
git add .
```

---

### Step 6: Commit your work

A commit is the actual save point. Give it a short, clear message that
describes what you did:

```bash
git commit -m "task 01: variables and input solution"
```

Good commit messages:
- `"task 01: completed all parts"`
- `"task 03: fix condition in Part B"`

Bad commit messages:
- `"done"`
- `"fix"`
- `"aaa"`

Check your commit was created:
```bash
git log --oneline
```

---

### Step 7: Push your branch to GitHub

Pushing means uploading your local branch to your fork on GitHub:

```bash
git push origin task-01
```

- `origin` = your fork on GitHub
- `task-01` = the branch you are pushing

---

### Step 8: Open a Pull Request (PR)

A Pull Request is how you say "I'm done — please review my work."

1. Go to your fork on GitHub: `https://github.com/YOUR-USERNAME/python-tasks`
2. You'll see a yellow banner: **"Compare & pull request"** — click it
3. Make sure the settings show:
   - **base repository**: main repo, branch `master`
   - **head repository**: your fork, branch `task-01`
4. Write a short title, e.g. `Task 01 - Variables and Input`
5. Click **Create Pull Request**

That's it — your work is submitted.

---

### Step 9: Making changes after review

If you get feedback and need to fix something:

1. Go back to your `solution.py` and make the changes
2. Stage and commit again:
```bash
git add tasks/task_01_variables_and_input/solution.py
git commit -m "task 01: fix after review"
git push origin task-01
```

The PR on GitHub updates automatically — no need to open a new one.

---

## Part 5 — Starting the Next Task

When you start a new task, go back to `master` first before creating a new branch:

```bash
git checkout master
git fetch upstream
git merge upstream/master
git checkout -b task-02
```

Never build task-02 on top of the task-01 branch — always branch off `master`.

---

## Quick Reference — Key Commands

| Command | What it does |
|---|---|
| `git status` | Show changed files |
| `git add <file>` | Stage a file |
| `git add .` | Stage all changed files |
| `git commit -m "message"` | Save a snapshot |
| `git push origin <branch>` | Upload branch to your fork |
| `git checkout -b <name>` | Create and switch to a new branch |
| `git checkout master` | Switch back to master |
| `git branch` | List branches, see current one |
| `git fetch upstream` | Download updates from the main repo |
| `git merge upstream/master` | Apply those updates locally |
| `git log --oneline` | See commit history |

---

## Common Mistakes

**"I edited master directly"**
Always create a branch first. If you accidentally worked on master, ask for help
before pushing.

**"I don't know what branch I'm on"**
Run `git branch` — the `*` shows your current branch.

**"I forgot to stage a file before committing"**
Run `git add <file>` then `git commit` again — you can make multiple commits.

**"My push was rejected"**
Usually means the remote has changes you don't have locally. Run:
```bash
git pull origin task-01
```
Then push again.
