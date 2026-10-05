Git Commands — Complete Quick Reference

A practical Git command reference for beginners and students.

1. Git Setup

Check Git version

git --version

Shows the installed Git version.

Set username

git config --global user.name "Your Name"

Set email

git config --global user.email "you@example.com"

Check configuration

git config --list

Get a specific configuration

git config user.name
git config user.email

2. Create or Start a Repository

Initialize a Git repository

git init

Creates a new .git repository in the current folder.

Clone a repository

git clone https://github.com/username/repository.git

Downloads an existing remote repository to your computer.

Clone into a specific folder

git clone https://github.com/username/repository.git my-project

3. Check Repository Status

Check status

git status

Shows modified, untracked, and staged files.

Show commit history

git log

Show compact commit history

git log --oneline

Show recent commits

git log -5

Show branches

git branch

4. Add Files

Add one file

git add filename.html

Add multiple files

git add file1.html file2.css

Add all changed files

git add .

Add all files including deletions

git add -A

5. Commit Changes

Create a commit

git commit -m "Your commit message"

Example:

git commit -m "Add homepage"

Commit all tracked modified files

git commit -am "Update project"

Note: -am does not include new untracked files. Use git add . first for new files.

Show a commit

git show COMMIT_ID

6. Branch Commands

Create a branch

git branch feature

Switch to a branch

git switch feature

Create and switch to a new branch

git switch -c feature

Older method

git checkout -b feature

Rename current branch

git branch -M main

Delete a local branch

git branch -d feature

Force delete a local branch

git branch -D feature

7. Remote Repository

Add GitHub remote

git remote add origin https://github.com/username/repository.git

Show remote repositories

git remote -v

Change remote URL

git remote set-url origin https://github.com/username/repository.git

Remove a remote

git remote remove origin

8. Push to GitHub

First push

git push -u origin main

The -u connects the local main branch with the remote main branch.

Normal push

git push

Push a specific branch

git push origin feature

Push all branches

git push --all

Delete a remote branch

git push origin --delete feature

9. Pull Changes

Pull changes from GitHub

git pull

Pull from a specific branch

git pull origin main

Fetch changes without merging

git fetch

Fetch all remote branches

git fetch --all

10. Merge Branches

Merge a branch into the current branch

git merge feature

Example:

git switch main
git merge feature

Abort a merge

git merge --abort

11. Git Diff

Show unstaged changes

git diff

Show staged changes

git diff --staged

Compare two commits

git diff COMMIT1 COMMIT2

12. Undo Changes

Unstage a file

git restore --staged filename

Discard changes in a file

git restore filename

Warning: This removes uncommitted changes in that file.

Restore all unstaged changes

git restore .

Undo the last commit but keep changes staged

git reset --soft HEAD~1

Undo the last commit and unstage changes

git reset --mixed HEAD~1

Undo the last commit and delete changes

git reset --hard HEAD~1

Warning: --hard can permanently remove uncommitted work.

13. Revert a Commit

Revert a commit safely

git revert COMMIT_ID

Creates a new commit that reverses the selected commit.

This is generally safer than rewriting shared history.

14. Stash

Save unfinished changes

git stash

Save with a message

git stash push -m "Work in progress"

List stashes

git stash list

Apply latest stash

git stash apply

Apply and remove latest stash

git stash pop

Delete a stash

git stash drop

Delete all stashes

git stash clear

15. Delete Files

Delete a file and stage the deletion

git rm filename

Stop tracking a file but keep it locally

git rm --cached filename

Delete a directory

git rm -r foldername

16. Rename Files

Rename a file

git mv oldname.html newname.html

Rename a folder

git mv old-folder new-folder

17. Tags

Create a tag

git tag v1.0

List tags

git tag

Create an annotated tag

git tag -a v1.0 -m "Version 1.0"

Push a tag

git push origin v1.0

Push all tags

git push --tags

Delete local tag

git tag -d v1.0

Delete remote tag

git push origin --delete v1.0

18. Git Log and History

Full history

git log

One-line history

git log --oneline

Graph view

git log --oneline --graph --all

Show files changed in commits

git log --stat

Search commit messages

git log --grep="keyword"

19. Find Information

Find who changed each line

git blame filename

Show a commit

git show COMMIT_ID

Show repository references

git reflog

reflog can help find commits or branch positions that are no longer visible in normal history.

20. GitHub Workflow

First-time project setup

cd my-project
git init
git branch -M main
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/username/repository.git
git push -u origin main

21. Normal Daily Workflow

After making changes:

git status
git add .
git commit -m "Describe your changes"
git pull
git push

A common alternative is to pull before committing when working with a shared remote:

git status
git pull
git add .
git commit -m "Describe your changes"
git push

22. Fix "Rejected — Fetch First"

If you get:

! [rejected] main -> main (fetch first)
error: failed to push some refs

Try:

git pull --rebase origin main
git push

If Git reports conflicts:

git status

Fix the conflicted files, then:

git add .
git rebase --continue
git push

If you want to cancel the rebase:

git rebase --abort

23. Git Pull with Rebase

Rebase while pulling

git pull --rebase origin main

Rebase current branch onto another branch

git rebase main

Continue after resolving conflicts

git add .
git rebase --continue

Abort rebase

git rebase --abort

Avoid rebasing commits that other people are already depending on unless you understand the consequences.

24. Resolve Merge Conflicts

When Git reports a conflict:

git status

Open the conflicted file and look for:

<<<<<<< HEAD
Your changes
=======
Other changes
>>>>>>> branch-name

Edit the file and keep the correct content.

Then:

git add .
git commit

For a rebase conflict:

git add .
git rebase --continue

25. .gitignore

Create a file named:

.gitignore

Example:

node_modules/
.env
*.log
.vscode/
__pycache__/

Check ignored files:

git status --ignored

26. Useful Git Commands

Help

git help

Help for a command

git help commit

Short help

git commit -h

Show current branch

git branch --show-current

Show remote URL

git remote get-url origin

Check repository

git fsck

Most Important Commands to Remember

For beginners, learn these first:

git --version
git config --global user.name "Your Name"
git config --global user.email "you@example.com"

git init
git clone URL

git status
git add .
git commit -m "message"

git branch
git switch -c branch-name
git switch main

git remote -v
git remote add origin URL

git pull
git push
git fetch

git merge
git diff

git log --oneline
git stash
git restore
git revert

Complete Git → GitHub Example

# 1. Go to your project
cd my-project

# 2. Initialize Git
git init

# 3. Rename the branch to main
git branch -M main

# 4. Check files
git status

# 5. Add files
git add .

# 6. Create commit
git commit -m "Initial commit"

# 7. Connect GitHub repository
git remote add origin https://github.com/username/repository.git

# 8. Push to GitHub
git push -u origin main

After that, for future changes:

git add .
git commit -m "Update project"
git pull --rebase origin main
git push

Quick Git Cheat Sheet

Command

Use

git init

Create Git repository

git clone URL

Download repository

git status

Check repository status

git add .

Stage all changes

git commit -m "message"

Save changes

git push

Upload changes

git pull

Download and integrate changes

git fetch

Download remote information

git branch

List branches

git switch branch

Change branch

git switch -c branch

Create and switch branch

git merge branch

Merge branch

git diff

See changes

git log

View history

git stash

Temporarily save changes

git restore file

Discard unstaged changes

git revert ID

Reverse a commit safely

git reset

Move/reset HEAD

git remote -v

View remote URL

git tag

Manage versions/tags

git rm file

Remove tracked file

git mv old new

Rename/move file

git blame file

See who changed lines

Important Difference

git add

Prepares changes for a commit.

git commit

Saves the prepared changes in local Git history.

git push

Uploads local commits to GitHub.

git pull

Gets changes from GitHub and integrates them into your local branch.

git fetch

Gets information from GitHub without automatically integrating the changes.

Recommended Basic Workflow

Edit files
   ↓
git status
   ↓
git add .
   ↓
git commit -m "message"
   ↓
git pull --rebase
   ↓
git push
   ↓
GitHub

Author

Kritan Basnet

Git command reference for learning and project work.