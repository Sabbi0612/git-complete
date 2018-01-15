# **Git-Complete**
## (Novice to Experienced Git User with Git Complete)

### Why Source Control?
* Backup (Ongoing backup known as Versioning)
* Undo Changes and Comparing versions
* Collaboration within large teams towards a single project. (Whom to Blame)
* Experimentation (Safely as change are not stored unless pushed)
* Switching Context
* Code reviews

### Types of Source/Version Control
* **Centralised** - Requires connection to the Centralised server for most of the operations (Network Connect required).
* **Decentralised/Distributed** - Most Operations are Local and do not require server (Network).

### Three States of GIT (Under three states comprise to create LOCAL):
* **Working Directory**
    * Contains all the project and application files.
    * May or may not be managed by git but git is aware of them.
* **Staging Area**
    * Pre-commit holding area and also referred as GIT Index.
    * This holds the queued changes ready to commit.
    * Files can be moved in/out of the staging area without affecting the git repo or history.
* **Commit - Git Repository (history)**
    * Within the working directory there is a hidden folder .git folder which contains the actual Git repository. Git repo manages the Git commit history. v1, v2 etc.

### Remote Repository (eg. GITHUB)
* Can be considered as the 4th State of GIT.
* This repository contains the above three states of its own.

### Branches are the timelines that contain our changes.
* Git provides us with default branch i.e master.

### Basic Git Commands:
```
git status
git add filename (for e.g. git add start.txt)
git commit -m “commit message”
git push origin master
git pull origin master
git commit -am “commit message”
git reset HEAD filename
git checkout — filename
git mv file-to-be-renamed new-name
```

### Creating Alias for git commands

* Suppose I want to make an alias for the command "git status" to "git s”
    * Command will be **git config --global alias.s “status"**
* Suppose I want to make an alias for the command "git log --all --online --graph --decorate" to "git hist”
    * Command will be **git config --global alias.hist “log --all --online --graph --decorate”**
* Important :
    * **--global** => tells that this command is for user level
    * **alias** => tells that we are creating an alias
    * **.s or .hist** refers to the new alias to be created
    * “**command exclusive of git keyword** that needs an alias”.

## Ways of renaming an existing file:
* **Renaming a file using Git**
    * Command - **git mv existing-filename new-filename**
    * This command is used for renaming the files using git.
    * (Important)This automatically adds the file to the staging area.

* **Renaming a file using bash**
    * Command - **mv existing-filename new-filename**
    * Running this command, for git it's like we have deleted an existing file and added a new file (with previous name).
    * To make git know that we have just renamed it we need to run another command **git add -A** to tell git that we have just renamed the file.

* If we want to rename the file back to what it was originally then in that case we can directly rename the file to what it was instead if using the git reset HEAD command and if the file is renamed to what it was originally then git will display a clean working directory.


### Ways of safely moving an existing file:
* To move a file to another folder using terminal
    * **git mv filename new-location**

* Move a file using bash or by Finder(folder structure)
    * **mv filename new-location** - Just like previously it seems to git that we have deleted a file and created a new file in the new location so to tell git that w have  just moved the file to a new location we need to do **git add -A**
