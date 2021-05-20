# Git Cheatsheet

## Workflow #1 - Start on GitHub -
#### Step 1 - create repo on GitHub & clone locally
```bash
git clone <url>
```

#### Step 2 - add content locally
```bash
git add .
git commint -m "message"
git push origin master
```

## Workflow #2 - Start Locally -
#### Step 1 - create a repo
```bash
echo "# this is my readme file" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main  #change name
```

#### Step 2 - create a Github repo & link
```bash
git remote add origin <repo url>
```

#### Step 3 - work locally then push
```bash
git push -u origin master
git push  # thereafter
```

## Git Configuration

#### Global Config File (outside repos)
```bash
brew install git  # install Git on Mac
git config -l  # view config settings
git config --global user.name "your name"
git config --global user.email "you@example.com"
git config --global color.ui auto  # coloring for Git
git config --global core.editor "code --wait"  # set up vscode, view git doc for other editors
git config --global credential.helper chache  # save my next token / password in cache, view docs for more on token & ssh
```

#### Local Config File (inside repo - config file inside .git)
```bash
git config --local user.name "chicken soup"  # use --local commands inside appropriate repo
git config --local user.email "chicken@gmail.com"
```

#### Common Aliases
```bash
git config --global alias.c commit  # git c = git commit
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status
git config --global alias.p push
git config --global alias.ll 'log --oneline'
git config --global alias.last 'log -1 HEAD --stat'
git config --global alias.cm 'commit -m'
git config --global alias.rv 'remote -v'
git config --global alias.d diff
```

## Create / Delete Repos
#### Create
```bash
git status  # make sure we are not in a repo
git init  # create a repo
git clone <url>  # clone remote repo
```

#### Delete
```bash
git rm <file>  # remove file fr working dir & staging area
rm -rf .git  # delete repo
```

#### Stash
```bash
git stash  # move changes in working dir into stash for later use
git stash pop  # apply stored stash content into working dir, & clear stash
git stash drop  # delete a stash 
```

## Staging & Committing
#### Staging
```bash
git add <file1>  # add/stage file1
git add <file1> <file2>  # add/stage file1 & file2
git add .  # add/stage all files
```

#### Un-staging
```bash
git reset <my_file.py>  # remove file fr staging area but keeps it in working dir
```

#### Commiting
```bash
git commit -m "commit message"  # commit
git commit -am "commit message"  # add & commit for tracked files only
git commit --amend -m "new message"  # modify commit message
```

## Git Reports
```bash
git --help  # see git commands
git status  # see staging area
git log  # shows commits
git log --oneline  # shows commits one per line
git diff  # changes in working dir (not staged)
git diff head  # changes in working dir (staged & unstaged)
git diff head <filename>  # changes in working dir (staged & unstaged) for <filename> file
git diff <branch1> <branch2>  # compare branches
git diff <branch1..branch2>  # compare branches
git diff --stages  # diff of what is stages but not commited
```

## Corrections
```bash
git restore  # restore working tree files
git checkout <hash>  # go back to that version in any public repo
git reset <hash>  # will reset to that hash location
git revert  # undo changes fr a commit. [revert keeps old version as opposed to reset which erases]
```

## Merge Conflicts
#### View Merge Conflicts
```bash
git diff  # complete conflict diff
git diff --base $file  # against base file
git diff --ours $file  # ag your changes
git diff --theirs $file  # ag other changes
```

#### Discard Conflicting Patch
```bash
git reset --hard
git rebase --skip
```

#### After Solving Conflicts, Merge
```bash
git add $conflicting_file  # do for all resolved files
git rebase --continue
```

## Git Ignore
```bash
touch .gitignore  # create .gitignore 
secrets.txt  # if secrets.txt is inside .gitignore file, then secrets.txt will be ignored
myJournal/  # the slash indicates it's a folder (will be ignored if inside .gitignore)
```

## Branching
#### Create
```bash
git branch  # show local branches
git branch -a  # show [-a] all branches (local & remote)
git branch <new branch>  # creates new branch
git branch -d <old branch>  # delete a branch
git branch -m <current-branch> <new-branch>  # rename branch
```

#### Merging
```bash
[1] git switch feature  # switch to feature branch
[2] git merge master # merge master into feature branch
git merge feature master # merge master into feature in one line
```

#### Switching
```bash
git switch <master>  # switch to branch
git switch -  # switch to previous branch
git switch -c <new-branch> # [-c] create & switch
```

## Remote Repos
#### Connections
```bash
git clone <url>  # clone remote repo
git remote add <name> <url>  # new connections to remote repo [name will be a shortcut to url]
git remote  # show remote connections
git remote -v  # show remote connections with urls
```

#### Local vs Remote Branches
```bash
git branch  # shows local branches
git branch -r  # shows remote branches
git switch <remote branch>  # adds branch to my local repo & will start tracking same name remote branch
```

#### Pushing
```bash
git push  # push local to remote
git push origin <branch A>  # push branch A to remote repo named origin
git push -u origin <branch B>  # upstream so next time use only 'git push'
git push --all  # push all branches
```

#### Fetching [partially import]
```bash
git fetch  # fetch fr remote to repo but not to working dir
git fetch <remote> <branch> # fetch specific branch
```

#### Pulling [fully import or fetch + merge]
```bash
git pull  # fetch & merge to local repo working dir
```

## How Does Git Work (behind the scene)
#### Hashing 
- Git uses SHA-1 hashing function.
- SHA-1 is deterministic.
- SHA-1 returns the same output for the same input.
- It is impossible to trace back the input or output without the hashing function.
- SHA-1 returns a 40 hexadecimal long number.
```bash
echo "michael" | git hash-object --stdin
f64c30d063c0fc3bfe1034a9f2efaac85574fa05
```