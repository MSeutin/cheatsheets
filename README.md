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
git commit -am "My feature is ready"
```

### 4) push branch
```shell
git push origin feature_name
```

### 5) review your code on commits page
### 6) create a merge request
### 7) your team lead reviews & merges it to main branch.

## Commands
### push an existing repository from the command line
```shell
git remote add origin https://github.com/MSeutin/test2.git
git branch -M main
git push -u origin main
```

### branches
```shell
git branch <branch-name> #create branch
git checkout <branch-name> #switch branch
git checkout -b <branch-name> #create branch & switch
git branch -d <branch-name> #delete branch while NOT on branch
```

