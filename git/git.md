## what is a git 
git is a open source version controll system .which used to manage the project

###  git init
* ***git init :-*** used to initilized the git repository

### git clone 
* ***git clone repository-url :-*** used to clone remote repository into local machine
* ***git clone -b branch-name repository-url :-*** used to clone a particular branch of a repository into a local machinr

```
example 1:-
    git clone https://github.com/nareshgupta99/learning-git.git

example 2:-
 git clone -b release https://github.com/nareshgupta99/learning-git.git
```

### git status 
* ***git status :-*** used to display the state of  working directory and the staging area.It lets you see which changes have been staged, which haven’t, and which files aren’t being tracked by Git. 

### git log
* ***git log :-*** used to display commited history of our repository

### pull Request
* ***pull request:-*** is performed by github ,or gitlab in a remote repository ,used to copy one branch into another branch

### To backup code / saves your local modifications away and reverts the working directory 
* ***git stash :-*** used when you want to record the current state of the working directory and the index, but want to go back to a clean working directory. The command saves your local modifications away and reverts the working directory to match the HEAD commit.

***example  :-*** Assume that i am working on a bug  bug-102 and i written some code towards to fixing the bug, while working on a bug, some high priority bug assigned to me name bug-103, to fix before bug-102,but i already written 200 lines of code towards to fixing bug, but working is not finished on bug-102 and not testesd properly,if i commit the changes in remote repositery increase the chances to project failure/or code failure, in this cituation i have to clean my working tree before working on a new bug bug-103, in order to backup my current working tree and to make my working tree clean **git stash** OR **git stash apply** command come into the picture.

* ***git stash appply :-*** Restore the backuped working tree

### git branch

* ***git branch :-*** To see the current working branch

* ***git checkout branch-name :-*** To switch b/w one branch to another branch

```
git checkout release

```

### git pull
* ***git pull :-*** used to get the latest code from remote repository to local Repository

### git push
* ***git push :-*** used to pushing the commited code from local repository to remote repository

### git add
* ***git add :-*** adding a modify file into staging area .
```
git add .
used to add all unstaged file into into a staging area
 
 git add --a 
working same as git add .



git add file-name1,file-name2 
used to add particular unstaged file into into a staging area

```
### git commit
* ***git commit -m message :-*** prepare a file for push from local to remote repository 
```
git commmit -m " bug-103 fixed"
```