# Useful Hg Commands

Most common `hg` commands in Mercurial

```bash
# Create
hg clone <repo-url> # Make a copy of an existing repository
hg init # Create a new repository

# Remote
hg pull # Pull changes
hg push # Push changes

# Work
hg update # Update working directory (or switch revisions)

# Change
hg add <filename> # Add files
hg commit -m "Commit message" # Commit the specified files or all outstanding changes
hg merge # Merge another revision into working directory
hg branch # Set or show the current branch
hg tag # Add one or more tags

# Patch
hg diff > my-patch # Save differences to my-patch
hg import --no-commit my-patch # Import my-patch without commit
```
