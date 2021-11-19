# Git & Github Cheatcheat

## Push Existing Repo to Github
Step 1: Create a Github Repo. <br>
Step 2: Initialize Git in the Project Folder. <br>
- `git status` to make sure you are not in a repo already.
- `git init` to create a repo - a hidden `.git` directory in your project folder.
- `git add .` or `git add -A` to include all files in the commit.
- `git commit -m "added my project"` to commit & message.
- `git branch -m <main>` to rename `master` to `main` if necessiry.
- `git remote add origin <git@github.com:sammy/my-new-project.git>` to add new remote origin onto Github, remote refers to a remote version of your local repo.
- `git push -u -f origin <main>` to push to Github, `-f` flag for 'force' will overwrite everything in the remote repo, the `-u` flag sets the remote origin as the default, this lets you later go `git push` or `git pull` without having to specify an origin.


