# Git Workflow

- **Untracked** -> **Staged** -> **Commit** -> **Unmodified** -> **Modified** -> **Staged** -> **Commit** -> **Unmodified** (working tree clean)

## Basic Git Configuration

git config --global user.name <username>
git config --global user.email <emailAddress>

## Git Commands

### Initialize Git Repository
git init
> Initializes the folder for git (creates `.git` directory).

### Adding Files to Staging Area
git add <filename>
> Moves untracked files to the staging area (for commit).

Alternative:
git add -A
> Adds all files to the staging area.

### Commit Staged Files
git commit -m "your commit message"
> Commits one or all staged files.

### Check Git Status
git status

### Undo Changes in Last Commit
git checkout <filename>
> Reverts to the last committed version of a file. If the file is damaged, this will restore it.

Alternative (for all files):
git checkout -f

### View Git Log
git log
> Shows the commit history.

Alternative:
git log -p -<number>
> Shows the latest 'n' commits and displays what changes were made.

### Compare Changes
git diff
> Compares modified files with the staged area.

git diff --staged
> Compares the staged area with the last commit.

### Direct Commit Without Staging
git commit -a -m "message"

### Remove Files from Staging Area
git rm --cached <filename>
> Moves a committed file or staged file back to the untracked area.

### Delete a File From Everywhere
git rm <filename>

### Summary of Git Status
git status -s
> Displays the status in summary format:

- M contact.html
- M index.html
- M terms.html

Files in both working and staging area:
- MM index.html

## .gitignore

The `.gitignore` file contains the names of files that Git will ignore. Example entries:

- mylog.log -> Ignore all files with this name (in any sub-folder).
- /mylog.log -> Only ignore this file in the current folder.
- *.log -> Ignore all files with a `.log` extension.
- folder/ -> Ignore a folder (Git ignores empty folders by default).

## Branching in Git

### Create a New Branch
git branch <new_branch>
> Creates a new branch.

### List Branches
git branch
> Shows all branches and marks the current branch with `*`.

### Switch Branches
git checkout <branch_name>

Alternative:
git checkout -b <new_branch>
> Creates and switches to a new branch.

### Merging Branches
When you're in the master branch:
git merge <branch_name>
> Merges updates from the specified branch into the master branch.

## Working with Remote Repositories

### Add Remote Repository
git remote add origin <repository_link>
> Adds a remote repository with the alias `origin`.

### Show Remote Repositories
git remote
> Shows remote repositories (e.g., `origin`).

git remote -v
> Displays the fetch and push URLs for the remotes.

### Change Remote URL
git remote set-url origin <new_repository_link>

### Pushing Code to GitHub
git push origin master
> Pushes code to the master branch.

Alternative:
git push -u origin <branch_name>
> Pushes code and sets upstream tracking. Next time, simply use:
git push
> Pushes directly to the tracked branch.

### Force Push
Use the `-f` flag with caution:
git push -f origin master
> Deletes all older data (commits) in the remote repository and pushes new data.

### Cloning a Repository
git clone <repository_link> <folder_name>
> Downloads code from the remote repository to a specified folder.

Without specifying a folder:
git clone <repository_link>
> Creates a new folder with the repository name.

### Pulling Updates from Remote Repository
git pull <remote> <branch>

Example:
git pull origin master

### SSH for Private Repositories
To push code to a private repository, generate an SSH key:
- Go to settings -> SSH key -> Generate a new SSH key.

---

Congratulations!
