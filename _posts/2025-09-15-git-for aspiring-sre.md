---
title: "GIT Essentials for Aspiring SRE"
date: 2025-09-15
layout: post
---



***

# Comprehensive Git Guide for Rookie and Aspiring SREs


***

## Introduction to Git

### What is Git?

Git is a version control system designed to track changes in files and coordinate work among multiple people. It helps you save snapshots of your project, collaborate safely, and rewind mistakes if necessary.

For an SRE, Git is essential for managing infrastructure code, automation scripts, and configuration safely and collaboratively.

***

## Git Fundamentals and Collaboration

### Setting Up Git

Before starting, configure your username and email:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```


### Creating and Working with a Repository

- Initialize a new Git repo in a folder to start tracking it:

```bash
mkdir my-first-git-project
cd my-first-git-project
git init
```

- Alternatively, clone an existing remote repo:

```bash
git clone https://github.com/some/repo.git
```


### Basic Commands

- Check which files have been modified or are new with:

```bash
git status
```

- Add files to be included in the next snapshot:

```bash
git add filename
```

- Save your changes with a message describing what you did:

```bash
git commit -m "Add initial script"
```


***

### Branching and Merging Basics

- List your branches and see which is active:

```bash
git branch
```

- Create a new branch for your work:

```bash
git branch feature-branch
```

- Switch to your new branch:

```bash
git switch feature-branch
```

- After working in your branch, merge those changes back into main:

```bash
git switch main
git merge feature-branch
```

- If there are merge conflicts, manually resolve them by editing conflicted files, staging, and completing the merge.

***

### Working with Remote Repositories

- Link your local repo to a remote repo (e.g., GitHub):

```bash
git remote add origin <remote-repo-URL>
```

- Push your commits online:

```bash
git push -u origin main
```

- Pull down changes others made:

```bash
git pull origin main
```


***

## Advanced Git Skills for SRE Workflows

### Rebasing

Rebasing reorganizes your commits to be "on top" of another branch’s tip, which keeps the project history clean.

```bash
git switch feature-branch
git rebase main
```

Resolve conflicts if any, then continue:

```bash
git add <conflicted-file>
git rebase --continue
```


***

### Git Stash

Temporarily save uncommitted changes to work on something else quickly:

```bash
git stash
git switch main
# do other work
git switch feature-branch
git stash pop
```


***

### Undoing Changes

- **Revert a commit safely:**

```bash
git revert <commit-hash>
```

- **Reset commits (use with caution):**
    - Unstage changes but keep them locally:

```bash
git reset HEAD <file>
```

    - Undo last commit but keep changes staged:

```bash
git reset --soft HEAD~1
```

    - Undo last commit and discard changes:

```bash
git reset --hard HEAD~1
```


***

### Viewing History and Diffs

- See concise commit logs:

```bash
git log --oneline
```

- Review differences between files or commits:

```bash
git diff
```


***

### Best Collaboration Practices

- Write clear, concise commit messages describing the “what” and “why.”
- Use `.gitignore` to avoid committing logs, secrets, or local config.
- Create pull requests and participate in code reviews.
- Tag releases for deployment tracking:

```bash
git tag -a v1.0 -m "Release version 1.0"
git push origin v1.0
```


***

### SRE-Specific Tips

- Manage infrastructure code and automation through Git (Terraform, Kubernetes YAML, etc.).
- Use branching and tagging to handle stable releases and hotfixes.
- Understand Git’s role in CI/CD pipelines and automated deployments.
- Keep backups of critical repositories for disaster recovery.
- Practice troubleshooting merge conflicts and history rewrites safely.

***

## Final Notes

This guide captures core and advanced Git knowledge tailored for SRE roles, from setup through collaboration and recovery. Keep practicing by working on real projects, and revisit these commands often. Git mastery will strengthen your reliability engineering work and career prospects.

***

