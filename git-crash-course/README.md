## Cloning 

We can clone three ways: HTTPS, SSH and Github CLI


since we are using github codespaces we'll create a 
temporary workspace in our directory


```sh
mkdir /workspaces/tmp 
cd /workspaces/tmp 
```

### HTTPS

```sh
git clone https://github.com/giriNova12/rough.git
```

### Git Hidden Folder

There is an hidden folder `.git` which tells you that our project
is a git repo.

if we want to create a git repo in a new project we create the folder 
and initiatize that repo using `git init`

```sh
mkdir /workspaces/tmp/new-project
cd /workspaces/tmp/new-project
git init
touch Readme.md
code Readme.md 
# check the status of our project
git status
# stage the changes by adding them 
git add .
# make changes to Readme.md 
git commit -m "add readme file in new project"
```
## Add

when we want to stage changes that will be included in the commit
we can use the `.` to add all possible files 

```sh
git add Readme.md
git add .
```

## Reset 

Reset allows you to move staged changes to unstaged 
this is useful when you want to revert all files not commited 


```sh
git add .
git reset
```

git reset will revert a git add

## Status 

Git status shows you what files will or will not be commited

```sh 
git status 
```

## Gitconfig file

The Gitconfig file is what stores your global configurations for 
git such as email, name, editor and more.

```sh
git config --list 
```

## log 

git log will show recent git commits to the git tree 

```sh
git log
```


## Commits

when we want to commit code we can write git commit which will open 
up the commit edit message in the editor of choice

```sh
# this commit after staging changes opens a editor
git commit
# this commit stages the changes and open a editor
git commit -a
# this commit stages and writes the message 
git commit -a -m "new commit"
# if already us the `add` to stage all unstaged files no need for -a 
git add .
git commit -m "new commit"

```

set the global editor

```sh
git config --global.core.editor emacs
```

## Push

when we want to push a repo to remote origin 
this will be succussful without writing origin only if 
we have already created clone repo from remote origin

```sh
git push 
```

if we want to push to remote origin 
you'll need to generate a Personal Access Token (PAT)
you will use PAT as password when you login

- give it access to Contents for commits

if not we have 3 options to securely push our repo
to remote origin using HTTPS, SSH and github CLI

- push to remote origin using HTTPS or SSH urls
- use github CLI to login to remote origin and push 


## HTTPS

using HTTPS to push current repository to remote origin

```sh
git push https://github.com/giriNova12/rough.git
```

## SSH

using ssh to push current repository to remote origin 

```sh
git push git@github.com:giriNova12/rough.git
```

## github CLI 

using github CLI to push current repository to remote origin 

```sh
gh autho login
```

```sh
gh clone gh repo clone giriNova12/rough
```



## Branches

To create new branch to the main branch 
```sh
git branch <name of the branch>
```
if we want to create new branch dev to origin 
```sh
git branch dev
```
To graphically view the changes and branches done 
to our repo install the extension 'git graph'
this helps us to visualize the repository tree

To create a commit in dev to view tree follow below 

```sh
git branch dev
# to view our branch - current branch will have *
# * main
#   dev
git branch
# switch to intended branch
git branch dev
# make necessary changes
code hello
git add .
git commit -m "first commit in dev branch"
git push -u origin dev

# return to main branch and verify
git switch main
git branch 

```


## Remotes

## Stashing

## Merging

