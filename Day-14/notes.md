# Git & GitHub Fundamentals

## Introduction

Git is a distributed version control system (VCS) that helps developers track changes in source code, collaborate with teams, and manage project history efficiently. GitHub is a cloud-based platform that hosts Git repositories, making collaboration easier.

---

What is Version Control?

Version Control is a system that records changes to files over time so you can:

- Track every modification.
- Restore previous versions.
- Collaborate with multiple developers.
- Prevent accidental data loss.

---

## Git vs GitHub

Git                              | GitHub
Version Control System           | Cloud hosting platform for Git repositories
Installed on local machine       | Accessible through a web browser
Tracks file changes              | Stores repositories online
Works offline                    | Requires internet for synchronization

---

## Key Git Concepts

### Repository (Repo)

A repository is a storage location that contains project files and their complete version history.

#### Types

- Local Repository
- Remote Repository

---

### Commit

A commit is a snapshot of your project at a specific point in time.

**Example:**

git commit -m "Added README file"

---

### Branch

A branch is an independent workspace used to develop features without affecting the main codebase.

#### Common branches:

- main
- feature
- bugfix

---

### Merge

Merge combines changes from one branch into another.

---

### Clone

Copies an existing GitHub repository to your local machine.

git clone <repository-url>

---

### Push

Uploads local commits to the remote repository.

git push origin main

---

### Pull

Downloads the latest changes from the remote repository.

git pull origin main

---

### Fetch

Downloads updates from the remote repository without merging them.

git fetch

---

### Status

Displays the current state of your repository.

git status

---

### Log

Shows the commit history.

git log

---

## Git Workflow

1. Create or clone a repository.
2. Modify project files.
3. Check repository status.
4. Stage changes using "git add".
5. Commit changes.
6. Push commits to GitHub.
7. Pull updates before continuing work.

---

## Essential Git Commands

git init
git clone <repository-url>
git status
git add .
git commit -m "Commit message"
git push origin main
git pull origin main
git branch
git checkout -b feature
git merge feature
git log
git fetch

---

## Why Git is Important for Cloud Engineers

- Stores Infrastructure as Code (Terraform, CloudFormation).
- Tracks Kubernetes YAML files.
- Supports CI/CD pipelines.
- Enables team collaboration.
- Maintains complete project history.
- Makes rollback to previous versions easy.

---

## Best Practices

- Write meaningful commit messages.
- Commit changes frequently.
- Pull before pushing.
- Use feature branches.
- Keep repositories organized.
- Never commit passwords, API keys, or secrets.
- Use ".gitignore" for unnecessary files.

---

## Advantages of Git

- Fast and efficient.
- Distributed architecture.
- Free and open source.
- Easy collaboration.
- Reliable version tracking.
- Supports branching and merging.

---

## Key Takeaways

- Git is a distributed version control system.
- GitHub hosts Git repositories online.
- Commits save project snapshots.
- Branches enable parallel development.
- Push uploads changes to GitHub.
- Pull retrieves updates from GitHub.
- Git is an essential skill for Cloud, DevOps, and Software Development.
