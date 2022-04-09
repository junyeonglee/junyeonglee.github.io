# Useful Git Commands

Most common `git` commands

```bash
# Config
git config -l --global # List all config (global)
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
git push origin master # Send changes to the master branch of your remote repository
git push --tags origin # Push all tags to remote repository

# Work
git branch # List, create, or delete branches
git checkout <branchname> # Switch branches

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
```
