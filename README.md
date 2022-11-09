# GitHub

## Feature Branch Workflow
### 1) clone project
```shell
git clone [url] #Clone (download) repo fr GitHub
#now i established a remote connection & can use
git pull
git push
```

### ...or create a new repository on the command line
```bash
echo "# test2" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/MSeutin/test2.git
git push -u origin main
```

### 2) create branch
```shell
git checkout -b feature_name
```

### 3) write code - commit changes
```shell
#add & commit all (1 step)
git commit -am "My feature is ready" #commit All + msg

#add & commit selected files (2 steps)
git add <file> #or <directory>
git commit -m "my message"
```

### 4) push branch
```shell
git push origin feature_name
```

### 5) review your code on commits page
### 6) create a merge request
### 7) your team lead reviews & merges it to main branch.

## Config
```shell
#checking your settings
git config --list

#set name that will be attached to your commits & tags
git config --global user.name “Your Name”

#set e-mail that will be attached to your commits and tags.
git config --global user.email “you@example.com”

#Enable some colorization of Git output
git config --global color.ui auto

#set main as default name (currently it's master with git init)
git config --global init.defaultBranch main

#set a text editor
git config --global core.editor "vim"

```

## Commands
### push an existing repository from the command line
```shell
git remote add origin https://github.com/MSeutin/test2.git
git branch -M main
git push -u origin main #see upstream option
git push --set-upstream ... #same as above <see upstream>
```

### branches
```shell
git branch <branch-name> #create branch
git checkout <branch-name> #switch branch
git checkout -b <branch-name> #create branch & switch
git branch -d <branch-name> #delete branch while NOT on branch
```

### remotes
```shell
#If repo cloned, origin is default name given
git remote #show remotes
git remote -v #same as above + url of remotes
git remote add <name> <url> #creates new remote connection

#changes remote name from 'origin' to 'destination'
git remote rename <origin> <destination> 

git remote remove <origin> #remove remote named 'origin'
git remote rm <paul> #same as above for 'paul'
```
