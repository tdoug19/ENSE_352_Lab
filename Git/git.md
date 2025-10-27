# 🧭 Git & GitHub Tutorial  

## 🧩  1. What is Git and Git Hub

Many people mix these up, but they serve different purposes. Here’s the breakdown 👇

---

## 🧠 What Is Git?

**Git** is a **version control system** — a tool that tracks changes in your files (usually code).  
It lets you:
- Keep a history of your work  
- Revert to earlier versions  
- Manage multiple branches  
- Work locally without the internet  

**Where it runs:** on your **local computer**

**Example commands:**
```bash
git init
git add .
git commit -m "Initial commit"
```

**Analogy:**  
Git is the **engine** that powers version tracking.

---

## ☁️ What Is GitHub?

**GitHub** is a **cloud-based platform** that hosts Git repositories online.  
It allows you to:
- Store your code on the web  
- Share projects with others  
- Collaborate using issues, pull requests, and branches  
- Contribute to open-source projects

**Where it runs:** on the **internet (GitHub servers)**

**Analogy:**  
GitHub is like **Google Drive for Git projects**, with teamwork features built in.

---

## ⚖️ Git vs GitHub Comparison

| Feature | **Git** | **GitHub** |
|----------|----------|-------------|
| Type | Version control software | Online hosting platform |
| Purpose | Track and manage changes | Host and collaborate on Git repositories |
| Works offline? | ✅ Yes | ❌ No |
| Installed on | Your computer | Website / cloud |
| Owner | Open-source (Linus Torvalds) | Microsoft |
| Example command | `git commit -m "message"` | `git push origin main` |
| Used for | Version control | Collaboration and storage |

---

## 💡 In Short

> **Git** = the technology (local version control)  
> **GitHub** = the platform (remote hosting and collaboration for Git projects)

---

## 🧱 2. Prerequisites

Make sure you have:

- [Git installed](https://git-scm.com/downloads)
- A [GitHub account](https://github.com)

## 🗂️ 3. Create a Local Project Folder

In your terminal (or PowerShell on Windows) (or Cygwin in Windows)

```bash
mkdir my-project
cd my-project
git init
git config --global user.name "Your Name"
git config --global user.email "your@email.com"  

```

✅ This creates an empty Git repository (a hidden `.git` folder).

### 🧰 Common Git Commands and Their Meanings

A quick reference for everyday Git usage.

---

#### 🔧 Setup & Configuration

| Command | Description |
|----------|--------------|
| `git config --global user.name "Your Name"` | Sets your global Git username. |
| `git config --global user.email "you@example.com"` | Sets your global Git email address. |

---

#### 🏗️ Creating & Initializing

| Command | Description |
|----------|--------------|
| `git init` | Initializes a new Git repository in the current folder. |
| `git clone <url>` | Makes a copy of a remote repository on your local machine. |

---

#### 📂 Tracking Files

| Command | Description |
|----------|--------------|
| `git status` | Shows the current state of the repository (changes, untracked files, etc.). |
| `git add <file>` | Stages a specific file for the next commit. |
| `git add .` | Stages all modified and new files. |
| `git rm <file>` | Removes a file from the repository and staging area. |

---

#### 💾 Saving Changes

| Command | Description |
|----------|--------------|
| `git commit -m "message"` | Records the staged changes with a descriptive message. |
| `git commit -am "message"` | Stages and commits all tracked files in one step. |
| `git log` | Displays the commit history. |
| `git diff` | Shows the differences between modified files and the last commit. |

---


#### 💡 Tip

You can use:
```bash
git help <command>
```

## 📝 4. Add a File and Commit It

Create a new "README.txt" file.  Use Explorer or the command line, just make sure it is in the root of your repository:

✅ Now Show the status of the repository.

```bash
git status
```

### 🔄 Git Workflow: Adding, Staging, and Committing

Understanding the Git workflow is key to using version control effectively.  
Git works in **three main areas**:  
1. **Working Directory**  
2. **Staging Area (Index)**  
3. **Repository (Local Repo)**

---

#### 🧱 1. Working Directory

This is where you **edit your files** — the actual folder on your computer.  
When you make changes, Git **notices** them but **doesn’t track** them automatically.

🧩 Example:
- You modify `README.txt`  
- Git detects the change but doesn’t include it in the next commit yet.

You can see what changed using:
```bash
git status
```
---

#### 📦 2. Staging Area

The **staging area** (also called the **index**) is where you tell Git **which files** you want to include in your next commit.

You stage files using:
```bash
git add <file>
```
or to add everything:
```bash
git add .
```

Think of it like packing items into a box before sealing it — the box is the **staging area**, and the commit is the **sealed package**.

---

#### 📝 3. Repository (Local Repo)

When you’re happy with the staged changes, you “seal the box” by committing them to your **local Git repository**.

You do this with:
```bash
git commit -m "Describe what you changed"
```

This creates a **snapshot** of your project — a permanent version you can always return to.


You can stage and commit in one step:
```bash
git commit -am "Describe what you changed"
```
---

## ✅ 4. Exercise
- make another changed to your README.txt file and stage and commit in one line.
- create another file and edit, add, stage and commit to your repository.


## ✅ 5. Check your progress by doing a Diff.

The `git diff` command shows **differences** between file versions in your Git repository.  
It’s one of the most useful commands for reviewing what changed before you commit.


### 🧩 1. Check Unstaged Changes

Use this to see what you changed **since the last commit**, but **not yet added** with `git add`.

```bash
git diff
```
- Lines beginning with + are additions, and lines with - are deletions.
- git log will show you the versions of your commits.
- git diff <commit1> <commit2> will show the differences.


## 🌐 6. Create a Remote Repository on GitHub

1. Go to [GitHub.com](https://github.com)  
2. Click the **“+”** in the top-right → **New repository**  
3. Name it `my-project`  
4. Leave **Initialize with README** **unchecked**  
5. Click **Create repository**  

GitHub will show you a page like this (keep it open!):

```bash
git remote add origin https://github.com/yourusername/my-project.git
git branch -M main
git push -u origin main

```
---

## 🔗 7. Connect Local Repo to Remote

In your terminal, copy and paste those commands:

```bash
git remote add origin https://github.com/yourusername/my-project.git
git branch -M main
git push -u origin main
```

✅ This links your local repo to GitHub and uploads your files.


## 🧭 8. Verify the Connection

Check the remote link:

```bash
git remote -v
```

Expected output:

```bash
origin  https://github.com/yourusername/my-project.git (fetch)
origin  https://github.com/yourusername/my-project.git (push)
```

Now refresh your GitHub repository page — your README and any other files you have 
created should appear 🎉  


## 🏗️ 9. Clone a Repository (HTTPS)
Now there is a connection between local machine and GitHub.  It is now possible to clone
this repository on any other maching with Git installed.  Go t0 a new empty folder (not in a git repsoitory) and clone.

```bash
git clone https://github.com/username/repo-name.git
```
✅ Git will create a new folder named repo-name with all the repository files and full history.

---

## 🗂️ 10. What File Types Should Go Under Revision Control (Git)

Not every file in your project should be tracked by Git.  
You only want to version **source files and important configuration files**, not temporary or generated files.

---

### 🧩 1. Source Code

These are files that define your project and can’t be easily regenerated.

.py, .js, .ts, .java, .cpp, .c, .cs, .rb, .php, .go, .swift, .rs

### 🧱 2. Markup & Template Files
These define the structure or layout of your app or website.
 .html, .xml, .json, .yaml, .yml, .md, .jinja, .ejs, .hbs

 ---

## 🚀 11. What's Next
- Branching
- Merging
- Forking
- Pull requests
- Working in Group Projects (Demo on Board)

 
### 🧰 Common Git Commands and Their Meanings

A quick reference for everyday Git usage.

---
#### 🔧 Setup & Configuration

| Command | Description |
|----------|--------------|
| `git config --global user.name "Your Name"` | Sets your global Git username. |
| `git config --global user.email "you@example.com"` | Sets your global Git email address. |
| `git config --list` | Displays all current Git configuration settings. |

---

#### 🏗️ Creating & Initializing

| Command | Description |
|----------|--------------|
| `git init` | Initializes a new Git repository in the current folder. |
| `git clone <url>` | Makes a copy of a remote repository on your local machine. |

---

#### 📂 Tracking Files

| Command | Description |
|----------|--------------|
| `git status` | Shows the current state of the repository (changes, untracked files, etc.). |
| `git add <file>` | Stages a specific file for the next commit. |
| `git add .` | Stages all modified and new files. |
| `git rm <file>` | Removes a file from the repository and staging area. |

---

#### 💾 Saving Changes

| Command | Description |
|----------|--------------|
| `git commit -m "message"` | Records the staged changes with a descriptive message. |
| `git commit -am "message"` | Stages and commits all tracked files in one step. |
| `git log` | Displays the commit history. |
| `git diff` | Shows the differences between modified files and the last commit. |

---

## 🌿 Branching & Merging

| Command | Description |
|----------|--------------|
| `git branch` | Lists all local branches. |
| `git branch <name>` | Creates a new branch. |
| `git checkout <branch>` | Switches to the specified branch. |
| `git switch <branch>` | Modern alternative to `git checkout`. |
| `git merge <branch>` | Merges another branch into the current branch. |
| `git branch -d <branch>` | Deletes a branch. |

---

## 🚀 Working with Remotes

| Command | Description |
|----------|--------------|
| `git remote -v` | Lists remote repositories. |
| `git remote add origin <url>` | Links your local repo to a remote one. |
| `git push -u origin main` | Pushes commits to the remote `main` branch and sets it as default. |
| `git push` | Uploads local commits to the remote repository. |
| `git pull` | Fetches and merges changes from the remote repository. |
| `git fetch` | Downloads commits, branches, and files from a remote repository (without merging). |

---

## 🧹 Undoing & Fixing Mistakes

| Command | Description |
|----------|--------------|
| `git restore <file>` | Discards changes in a file (before commit). |
| `git reset <file>` | Unstages a file but keeps changes. |
| `git reset --hard` | Resets the repository to the last commit (⚠️ erases changes). |
| `git revert <commit>` | Creates a new commit that undoes a specific previous commit. |

---

## 📦 Tags & Versions

| Command | Description |
|----------|--------------|
| `git tag` | Lists all tags. |
| `git tag <tagname>` | Creates a new tag. |
| `git push origin <tagname>` | Pushes a specific tag to the remote repository. |
| `git push origin --tags` | Pushes all tags to the remote. |

---

## 🕵️ Viewing History

| Command | Description |
|----------|--------------|
| `git show` | Shows details of a specific commit. |
| `git log --oneline --graph` | Displays the commit history in a simplified graphical format. |
| `git blame <file>` | Shows who made changes to each line of a file. |

---

