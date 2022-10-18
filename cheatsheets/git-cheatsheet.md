# Git Cheat Sheet

Most common `git` commands

```bash
# Config
git config --global -l # List all config (global)
git config --global user.name "junyeonglee" # Set username
git config --global user.email "junyeonglee@email.com" # Set email
git config --global user.name # Get username

# Create
git clone <repo-url> # Check out a repository
git init # Create a new local repository

# Remote
git remote add origin <server> # Add a remote server
git remote -v # List all remote repositories
git pull # Fetch and merge changes on the remote server to your working directory
git push origin master # Send changes to remote repository' master branch
git push --tags origin # Push all tags to remote repository

# Work
git branch # List, create, or delete branches
git checkout <branchname> # Switch branches
git checkout -b <branchname> # Causes a new branch to be created

# Change
git add <filename> # Add files
git commit -m "Commit message" # Commit
git merge <branchname> # Merge a different branch into your active branch
git tag 1.0.0 <commitID> # Mark a significant changeset

# Undo local changes
git checkout -- <filename> # Discard changes on file
git fetch origin # Fetch the latest history from the server
git reset --hard origin/master # Drop all local changes and commits

# Patch
git diff > my-patch
git apply my-patch

# Stash
git stash # stash the changes in a dirty working directory away
git stash pop # remove from stash list and apply it on top of the current working tree state

# Pull 
git pull origin foo # git fetch origin foo; git merge origin/foo
git pull origin bar~1:bugFix # git fetch origin bar~1:bugFix; git merge bugFix
```
