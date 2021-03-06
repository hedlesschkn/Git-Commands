### seting up github
make a github account  
download the latest version of git  
 - https://git-scm.com/downloads  
set username in git
 - $ git config --global user.name "My Name"
set commit email address
 - $ git config --global user.email "email@example.com"
 

### starting from an existing project  
https://kbroman.org/github_tutorial/pages/init.html  
must be connected with SSH first  
cd to existing directory  
git init  
git add --all  
git commit -m "[message]"  
#### connect it to github  
go to github.com, create a new repo.  MUST BE EMPTY, NO README OR GITIGNORE  
from green 'clone or download' choose 'Use SSH"  
$ git remote add origin git@github.com:username/new_repo  
$ git push -u origin master  
if you made a readme this will fail and you need to do
$ git pull --rebase  
then  
$ git push  

### starting from github  
go to github.com, create a new repo  
cd to directory (I use Documents/Arduino)  
git clone [URL]  
git status (shows difference between local git and github cloud)  
git add [filename] (adds any changes or files by name to lcoal git)  
 - git add . (add everything in the directory)  
 - git add -A (add all)  
 
git commit -m "[message]" (commits change to local git w/ message)  
can also do git commit -a -m "[message]" (this does add and commit in one command)  
git push (sync local git with github cloud)  

git pull (pulls from github cloud to git local)  

----
revisioning (versioning)

git log  
git log --summary (includes created files)  
 - :q leaves log  
git checkout hash
 - can also add tags for version names (more human readable and can be accessed by tag instead of hash later)
----

more:  
git (gives list of commands)  
esc :wq (escapes and saves from a 'you didn't give a message' warning from a commit or lets you do multiline)  
   
remove a git:  
linux:  
rm -rf .git  
windows:  
del /F /S /Q /A .git  
rmdir /s .git  
cd ..  
rmdir /s <folder>  

first commit will ask:  
git config --global user.email "you@example.com"  
git config --global user.name "Your Name"  

alias:  
echo @dir %* > %systemroot%\system32\ls.bat  

add SSH:  
generate ssh key  
C:\Users\USERNAME\.ssh\id_rsa.pub (open with text editor)
https://help.github.com/en/enterprise/2.15/user/articles/adding-a-new-ssh-key-to-your-github-account  

Do a Pull Request:
fork the original  
clone your new forked repo (not the original)  
make modifications  
add, commit, push  
in github.com, from your repo, 'new pull request' button  
original will recieve request and accept or deny  

----

Git Commands
============

_A list of my commonly used Git commands_

*If you are interested in my Git aliases, have a look at my `.bash_profile`, found here: https://github.com/joshnh/bash_profile/blob/master/.bash_profile*

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

