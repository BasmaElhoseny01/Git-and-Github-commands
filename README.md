# Git Commands and GitHub

### 1. git init 
to turn current directory to a git repository

The git remote command will let you manage and interact with remote repositories.

D:\trial>git remote
The Terminal application running the git remote command. No output is displayed since this repository does not have a connection to a remote.
<hr>

### 2.commit chages to git
D:\trial>git add .
D:\trial>git commit -m "initial commit"

[master (root-commit) c725810] initial commit
 1 file changed, 45 insertions(+)
 create mode 100644 index.html

D:\trial>git log --oneline --graph --decorate --all
* c725810 (HEAD -> master) initial commit
<hr>

### 3.Push Commits
To send local commits to a remote repository you need to use the git push command. You provide the remote short name and then you supply the name of the branch that contains the commits you want to push:
$ git push <remote-shortname> <branch>

D:\trial>git log --oneline --graph --decorate --all
* c725810 (HEAD -> master, origin/master) initial commit

The word "origin", here, is referred to as a "shortname". A shortname is just a short and easy way to refer to the location of the remote repository. A shortname is local to the current repository (as in, your local repository). The word "origin" is the defacto name that's used to refer to the main remote repository. 
It's possible to rename this to something else, but typically it's left as "origin".
<hr>

### 4.Pull Commits
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
<hr>

### 5.Fetch 
$ git fetch origin master
Git fetch is used to retrieve commits from a remote repository's branch but it does not automatically merge the local branch with the remote tracking branch after those commits have been received.

refer to demo when to use fetch vs pull
https://www.youtube.com/watch?v=jwyQUfE1Eqw&t=61s
<hr>

### 6.Forking
Note forking isn't a git command so we can't run it on the cmd it provided by the hosting environment (GitHub)
Forking a repository creates an identical copy of the original repository and moves this copy to your account.
Modifying your forked repository does not alter the original repository in any way.
<hr>

### 7.Branching

list local branches
git branch

list remote branches
git branch -r

create new branch
git branch new_branch

swicth to the new branch 
git checkout -b ＜new-branch＞

push changes of the new branch
git push <remote> <branch>

delete a branch
git branch --delete <branchname>


Changing name of a bracnh
The steps to change a git branch name are:
1.Rename the Git branch locally with the git branch -m new-branch-name command
2.Push the new branch to your GitHub or GitLab repo
3.Delete the branch with the old name from your remote repo
<hr>

### 8.Git log
The git log command is extremely powerful, and you can use it to discover a lot about a repository. But it can be especially helpful to discover information about a repository that you're collaborating on with others. You can use git log to:

group commits by author with git shortlog
  $ git shortlog
filter commits with the --author flag

  $ git log --author="Richard Kalehoff"
filter commits using the --grep flag

$ git log --grep="border radius issue in Safari"
<hr> 
### 9.pull request
You have created a fork from another one's repo you have made some changes in your copy and want to ask the owner to add these changes in the original repo(the onr you forked from)
so send him a oull request and he either accept to merge thiese changes to his repo or not

https://www.youtube.com/watch?v=twLr9ndsf90&t=47s
https://www.youtube.com/watch?v=d3AGtKmHxUk
<hr>

### 10.Stay in sync with source project
While you're working on a topic branch(branch you made after forking from repo to have changes in acertain topic) of changes that you want to make to a repository, that repository will probably be receiving updates of its own from the original authors.

1.Star:
If you want to keep up-to-date with the Repository, GitHub offers a convenient way to keep track of repositories - it lets you star repositories
Starring is helpful if you want to keep track of certain repositories. But it's not entirely helpful if you need to actively keep up with a repositories development because you have to manually go to the stars page to view the repositories and see if they've changed

2.watch:
If you want to keep up-to-date with the Repository, GitHub offers a convenient way to keep track of repositories - it lets you star repositories
If you're working on a repository quite often, then I'd suggest setting the watch setting to "Watching". This way GitHub will notify you whenever anything happens with the repository like people pushing changes to the repository, new issues being created, or comments being added to existing issues.


Including Upstream Changes:(how to take changes made by the owner of repo to yours)
https://www.youtube.com/watch?v=VvoC6hN6FjU
<hr>
### 11.Squash Commits:
It combines severla commits into a single commit
https://www.youtube.com/watch?v=H5JqcdIB5y0

$ git rebase -i HEAD~3
merging the last 3 commits into a single commit and the 3 are delted and head of the current branch will point to the new commit(combined)
