# GitHub_all_commands

# Setup Commands
git config --global user.name "Your Name": Set the username for commits.

git config --global user.email "your.email@example.com": Set the email for commits.
git config --global color.ui auto: Enable automatic command line coloring.
git config --list: List all configuration settings.

# Repository Commands
git init: Initialize a new Git repository.
git clone <repository>: Clone an existing repository.

# Working with Branches
git branch: List all local branches.
git branch -a: List all branches (local and remote).
git branch <branch-name>: Create a new branch.
git checkout <branch-name>: Switch to a branch.
git checkout -b <branch-name>: Create and switch to a new branch.
git merge <branch-name>: Merge a branch into the current branch.
git branch -d <branch-name>: Delete a branch.

# Staging and Committing
git status: Show the status of changes.
git add <file>: Stage a file for commit.
git add .: Stage all changes in the current directory for commit.
git commit -m "Commit message": Commit staged changes with a message.
git commit -am "Commit message": Stage and commit all changes with a message.

# Remote Repositories
git remote -v: List remote repositories.
git remote add <name> <url>: Add a new remote repository.
git fetch <remote>: Fetch changes from a remote repository.
git pull <remote> <branch>: Pull changes from a remote branch.
git push <remote> <branch>: Push changes to a remote branch.

# Viewing History
git log: View commit history.
git log --oneline: View commit history in a compact form.
git log --graph: View commit history with a graph.

# Undoing Changes
git reset <file>: Unstage a file.
git reset --hard <commit>: Reset the working directory and index to a specific commit.
git revert <commit>: Create a new commit that reverts a specific commit.
git checkout -- <file>: Discard changes in a file.

# Stash Commands
git stash: Stash changes in the working directory.
git stash apply: Apply stashed changes.
git stash pop: Apply and remove stashed changes.
git stash list: List all stashes.
git stash drop: Remove a specific stash.

# Tagging
git tag: List all tags.
git tag <tag-name>: Create a new tag.
git tag -a <tag-name> -m "Tag message": Create an annotated tag.
git push <remote> <tag-name>: Push a tag to a remote repository.
git push --tags: Push all tags to a remote repository.

# Miscellaneous
git diff: Show changes between commits, commit and working tree, etc.
git blame <file>: Show what revision and author last modified each line of a file.
git show <commit>: Show various types of objects.
git archive: Create an archive of files from a named tree.
git cherry-pick <commit>: Apply the changes introduced by some existing commits.
git rebase <branch>: Reapply commits on top of another base tip.
git bisect: Use binary search to find the commit that introduced a bug.

# Cleaning Up
git clean -f: Remove untracked files from the working directory.
git gc: Cleanup unnecessary files and optimize the local repository.

These commands form the foundation of Git and cover most of the typical workflows you might encounter. As you become more comfortable with Git, you'll find additional commands and options to suit your specific needs.



# git pull vs git fetch

git pull:
Combines two commands: git fetch followed by git merge.
Downloads changes from a remote repository and directly merges them into the current branch.
Syntax: git pull <remote> <branch>
Example: git pull origin main

git fetch:
Downloads changes from a remote repository but does not merge them.
Updates the local copy of the remote branches.
Allows you to review changes before merging.
Syntax: git fetch <remote>
Example: git fetch origin

In essence, git pull automatically merges the fetched changes into your working branch, while git fetch only updates the remote tracking branches, allowing you to inspect changes and decide how to integrate them.

# git rebase
git rebase:
Reapplies commits on top of another base tip.
Moves or combines a sequence of commits to a new base commit.
Changes the commit history, which can lead to a cleaner, more linear project history.

How it works:
Identify the base commit: The common ancestor of the current branch and the target branch.
Reapply commits: Takes the commits from your branch and applies them on top of the target branch.
New commit history: Creates new commits for each commit in your branch.

Common usage:
Integrating changes from one branch into another in a linear history.
Keeping a feature branch up-to-date with the latest changes from the main branch.
Syntax:

git rebase <branch>
Example: git rebase main
Example Workflow:
Switch to the branch you want to rebase: git checkout feature-branch
Rebase onto the target branch: git rebase main
Resolve any conflicts that arise during the rebase process.
If you need to abort the rebase: git rebase --abort
If you successfully resolve conflicts: git rebase --continue
Advantages:
Cleaner commit history.
Avoids the creation of unnecessary merge commits.
Caution:
Rewriting history can cause issues for collaborators if they have based work on the original commits.
Avoid using rebase on public branches to prevent disrupting the commit history for others.
By understanding and utilizing git fetch, git pull, and git rebase, you can maintain a more organized and efficient workflow in your projects.
