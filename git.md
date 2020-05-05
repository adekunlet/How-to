========================================
# Frequently used git commands
========================================

========================================
# Git Tagging
========================================
https://git-scm.com/book/en/v2/Git-Basics-Tagging
## Annotated Tags</br>
Creating an annotated tag in Git is simple. The easiest way is to specify -a when you run the tag command:</br>

$ git tag -a v1.4 -m "my version 1.4"</br>

You can see the tag data along with the commit that was tagged by using the git show command

## Lightweight Tags
Another way to tag commits is with a lightweight tag. This is basically the commit checksum stored in a file — no other information is kept. To create a lightweight tag, don’t supply any of the -a, -s, or -m options, just provide a tag name:

$ git tag v1.4-lw

## to view tags
$ git tag

## Tags sample workflow
Create a lightweight tag</br>
Create an annotated tag</br>
Push the tags to the remote repository</br>
git checkout master

# Lightweight tag
git tag my_lightweight_tag

# Annotated tag
git tag -a v1.0 -m ‘Version 1.0’
git tag

git push origin --tags

========================================
# Git remote commands
========================================

git remote add new-repo-name git-repo-remote-add

git remote -v

git push repo-name branch-name
  
# What you need to do to update the remote is to force push your local changes to master:

git checkout master

git reset --hard e3f1e37

git push --force origin master

# Then to prove it (it won't print any diff)

git diff master..origin/master

========================================
# Branching and merging strategy
========================================

https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging

# Github Commands
## Standard Working Approach
### From feature branch get latest from master the push to remote repo before doing pull request:
- from feature branch
git commit -m 'new feature added'
git checkout master
git pull origin master
git checkout feature
git rebase master
- fix any merge issues
git commit -m "description of change"
git push feature
- create pull request 

To undo git add before a commit: Run git reset <file> or git reset to unstage all changes.

# If you are having difficulty with a pull into develop from source that should not have changed anyway use use below command the reset

git reset --hard HEAD

# If you have changes you want to keep and want to refrash master then this will get latest commits from master and replay your changes on top

git rebase master
# Provide credentials during git clone

git clone https://username:password@remote

Git Commands
============

_A list of my commonly used Git commands_

*If you are interested in my Git aliases, have a look at my `.bash_profile`, found here: https://github.com/joshnh/bash_profile/blob/master/.bash_profile*


https://help.github.com/en/articles/changing-a-remotes-url

--

### Getting & Creating Projects

| Command | Description |
| ------- | ----------- |
| `git init` | Initialize a local Git repository |
| `git clone ssh://git@github.com/[username]/[repository-name].git` | Create a local copy of a remote repository |

### Basic Snapshotting

| Command | Description |
| ------- | ----------- |
| `git status` | Check status |
| `git add [file-name.txt]` | Add a file to the staging area |
| `git add -A` | Add all new and changed files to the staging area |
| `git commit -m "[commit message]"` | Commit changes |
| `git rm -r [file-name.txt]` | Remove a file (or folder) |

### Branching & Merging

| Command | Description |
| ------- | ----------- |
| `git branch` | List branches (the asterisk denotes the current branch) |
| `git branch -a` | List all branches (local and remote) |
| `git branch [branch name]` | Create a new branch |
| `git branch -d [branch name]` | Delete a branch |
| `git push origin --delete [branch name]` | Delete a remote branch |
| `git checkout -b [branch name]` | Create a new branch and switch to it |
| `git checkout -b [branch name] origin/[branch name]` | Clone a remote branch and switch to it |
| `git branch -m [old branch name] [new branch name]` | Rename a local branch |
| `git checkout [branch name]` | Switch to a branch |
| `git checkout -` | Switch to the branch last checked out |
| `git checkout -- [file-name.txt]` | Discard changes to a file |
| `git merge [branch name]` | Merge a branch into the active branch |
| `git merge [source branch] [target branch]` | Merge a branch into a target branch |
| `git stash` | Stash changes in a dirty working directory |
| `git stash clear` | Remove all stashed entries |

### Sharing & Updating Projects

| Command | Description |
| ------- | ----------- |
| `git push origin [branch name]` | Push a branch to your remote repository |
| `git push -u origin [branch name]` | Push changes to remote repository (and remember the branch) |
| `git push` | Push changes to remote repository (remembered branch) |
| `git push origin --delete [branch name]` | Delete a remote branch |
| `git pull` | Update local repository to the newest commit |
| `git pull origin [branch name]` | Pull changes from remote repository |
| `git remote add origin ssh://git@github.com/[username]/[repository-name].git` | Add a remote repository |
| `git remote set-url origin ssh://git@github.com/[username]/[repository-name].git` | Set a repository's origin branch to SSH |

### Inspection & Comparison

| Command | Description |
| ------- | ----------- |
| `git log` | View changes |
| `git log --summary` | View changes (detailed) |
| `git diff [source branch] [target branch]` | Preview changes before merging |

### working with remotes
https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes
