# trail
1. git init 
to turn current directory to a git repository
=============================================================================================================================================================
The git remote command will let you manage and interact with remote repositories.

D:\trial>git remote
The Terminal application running the git remote command. No output is displayed since this repository does not have a connection to a remote.
============================================================================================================================================================
2.commit chages to git
D:\trial>git add .
D:\trial>git commit -m "initial commit"

[master (root-commit) c725810] initial commit
 1 file changed, 45 insertions(+)
 create mode 100644 index.html

D:\trial>git log --oneline --graph --decorate --all
* c725810 (HEAD -> master) initial commit
=============================================================================================================================================================
3.Push Commits
To send local commits to a remote repository you need to use the git push command. You provide the remote short name and then you supply the name of the branch that contains the commits you want to push:
$ git push <remote-shortname> <branch>

D:\trial>git log --oneline --graph --decorate --all
* c725810 (HEAD -> master, origin/master) initial commit

The word "origin", here, is referred to as a "shortname". A shortname is just a short and easy way to refer to the location of the remote repository. A shortname is local to the current repository (as in, your local repository). The word "origin" is the defacto name that's used to refer to the main remote repository. 
It's possible to rename this to something else, but typically it's left as "origin".
===============================================================================================================================================================
4.Pull Commits
$ git pull origin master


When git pull is run, the following things happen:
the commit(s) on the remote branch are copied to the local repository
the local tracking branch (origin/master) is moved to point to the most recent commit
the local tracking branch (origin/master) is merged into the local branch (master)

D:\trial>git pull origin master
From https://github.com/BasmaElhoseny01/trail
 * branch            master     -> FETCH_HEAD
Updating c725810..85a7e74
Fast-forward
 index.html | 4 +---
 1 file changed, 1 insertion(+), 3 deletions(-)

D:\trial>git log --oneline --graph --decorate --all
* 85a7e74 (HEAD -> master, origin/master) Update index.html
* c725810 initial commit

https://www.youtube.com/watch?v=MjNU2LTDVAA
============================================================================================================================================================
5.Fetch 
$ git fetch origin master
Git fetch is used to retrieve commits from a remote repository's branch but it does not automatically merge the local branch with the remote tracking branch after those commits have been received.

refer to demo when to use fetch vs pull
https://www.youtube.com/watch?v=jwyQUfE1Eqw&t=61s
=======================================================================================================================================================
6.Forking
Note forking isn't a git command so we can't run it on the cmd it provided by the hosting environment (GitHub)
