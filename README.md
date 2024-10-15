## Overview

This guide provides an overview of Git commands within a three-tier architecture consisting of the Working Directory, Staging Area, and Local Repository. It outlines how to initialize a Git repository, configure Git settings, perform common Git operations, and manage files and folders effectively.

## Table of Contents

- [Three-Tier Architecture](#three-tier-architecture)
- [Initializing a Repository](#initializing-a-repository)
- [Configuring Git](#configuring-git)
- [Directory Commands](#directory-commands)
- [Git Commands](#git-commands)
- [File and Folder Operations](#file-and-folder-operations)
- [Working Directory vs Staging Area](#working-directory-vs-staging-area)
- [Skip Staging Area](#skip-staging-area)
- [Adding Files to GitHub](#adding-files-to-github)
- [Branch Management](#branch-management)
- [Git Log Commands](#git-log-commands)
- [Change Commit](#change-commit)
- [Stage to Unstage](#stage-to-unstage)
- [Go Back to Last Commit](#go-back-to-last-commit)
- [GitHub Integration](#github-integration)
- [Adding SSH Key to GitHub](#adding-ssh-key-to-github)
- [Aliases](#aliases)

## Three-Tier Architecture

1. **Working Directory**: The local environment where files are modified.
2. **Staging Area**: The intermediate area where changes are prepared before committing.
3. **Local Repository**: The version-controlled repository storing commits and history.

## Initializing a Repository

```bash
git init
```
- Initializes an empty Git repository in the current directory.

## Configuring Git

```bash
git config --global user.name "Name"
git config --global user.email "Email"
git config --global --edit
```
- Sets the username and email for Git commits.
- Opens the global Git configuration file for editing.

## Directory Commands

```bash
pwd                    # Present Working Directory
cd fileName            # Change directory
```
- **Folder open in PowerShell**: Use Shift + Right-click to change directory.

## Git Commands

```bash
git init               # Initialize Repository
git status             # Tracking Status
git add --a            # Add all files to the staging area
git add "FileName"     # Add a single file to the staging area
git commit -m "info."  # Commit changes
git log                # Check all commits
rm -rf .git            # Delete repository for the folder
git clone "link"       # Clone a repository
```

## File and Folder Operations

```bash
touch fileName                # Create a file
touch .gitignore              # Create a .gitignore file
```

### In `.gitignore` file
- `*.log`                   # Ignore all log files
- `node/`                   # Ignore a folder
- `/dir/`                   # Ignore an upper folder
- `node/dir`                # Ignore inside a folder

## Working Directory vs Staging Area

```bash
git diff                     # Show changes
git diff --staged            # Show changes between last commit and staging area
```

## Skip Staging Area

```bash
git commit -a -m "FileName"  # Commit without staging
git add "FileName"           # Add a single file
git rm FileName              # Remove a file
git mv FileName NewFileName  # Rename a file
rm --cached nv.txt           # Change modified to untracked
```

## Adding Files to GitHub

```bash
git push -u origin main      # Add and push files to GitHub (default branch: main)
```

## Branch Management

```bash
git branch                   # List all branches
git checkout -b "fileName"   # Create a new branch and switch to it
git checkout branchName       # Switch branches
git merge 'branchName'        # Merge a branch into the main branch
git branch -v                 # See last commits (branch)
git branch --merged           # Show merged branches
git branch --no-merged        # Show branches not merged
git branch -d fileName        # Delete a branch
git push -d origin fileName   # Delete a branch in remote
```

## Git Log Commands

```bash
git log -p                    # Show commit changes
git log -p -n                 # Show 'n' number of commits
git log --state               # Show commit statistics
git log --pretty=oneline      # Show commits on a single line
git log --pretty=short        # Show commits in a short format
git log --since=2.days        # Show commits since a specific time frame
git log --pretty=format:"..."  # Customize log output format
```

## Change Commit

```bash
git commit --amend           # Modify the last commit
```

## Stage to Unstage

```bash
git restore --staged fileName  # Undo staging changes
```

## Go Back to Last Commit

```bash
git checkout (github filename)  # Revert changes to the last commit
git checkout -f                  # Revert all files
```

## GitHub Integration

```bash
git remote                       # Check remote repositories
git remote add origin (URL)      # Add a remote repository
git remote -v                    # Show remote repositories and their URLs
```

## Adding SSH Key to GitHub

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"  # Generate an SSH key
eval "$(ssh-agent -s)"                          # Start the SSH agent
ssh-add ~/.ssh/id_ed25519                       # Add the SSH key to the SSH agent
tail ~/.ssh/id_ed25519.pub                      # Copy the SSH key for GitHub
```

## Aliases

```bash
git config --global alias.st status          # Set alias 'st' for 'status'
git config --global alias.unstage 'restore --staged --'  # Set alias 'unstage'
git config --global alias.last 'log -p -1'  # Set alias 'last' for 'log -p -1'
```

## Conclusion

This guide serves as a comprehensive reference for utilizing Git in a three-tier architecture. For more detailed information, refer to the official [Git documentation](https://git-scm.com/doc).
