# Git

### Configure user information for all local repositories
```bash
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@mail.com

# enables helpful colorization of command line output
$ git config --global color.ui auto

# list and show Git config settings
$ git config -l
```

### Initialize a new git repository
```bash
$ git init
```

### Add a file to the staging area
```bash
$ git add <file>

# to add all files
$ git add .

# to add only certain files
$ git add <fil*>
```

### Undoes all commits after [commit], preserving changes locally
```bash
$ git reset [commit]
```

### Discards all history and changes back to the specified commit
```bash
$ git reset --hard [commit]
```

### Displays the difference between files in two commits or between a commit and your current repository
```bash
$ git diff
```

### Show the status of the current repository including staged, unstaged, and untracked files
```bash
$ git status
```

### Commit changes with a message
```bash
$ git commit -m "message"
```

### Lists version history for the current branch
```bash
$ git log
```

### Clone (download) a repository that already exists on a remote repository
```bash
$ git clone [url]
```

### List all the local branches
```bash
$ git branch
```

### Create a new branch locally
```bash
$ git branch <branch-name>
```

### Delete a branch
```bash
$ git branch -d <branch-name>
```

### Rename the current working branch
```bash
$ git branch -m <new-branch-name>
```

### Merges the provided branch with the current working branch
```bash
$ git merge <branch-name>
```

### Switch from current branch to another one
```bash
$ git checkout <branch-name>
```

### Create a new branch and switch to it immediately
```bash
$ git checkout -b <branch-name>
```

### Uploads a local branch commits to a remote repository
```bash
# Just remember to add -u to create the branch upstream
$ git push -u origin <branch-name>
```

### Updates your current local working branch with all new commits from the corresponding remote branch
```bash
# git pull is a combination of git fetch and git merge
$ git pull
```

### Remove tracked files from the current working directory
```bash
$ git rm <filename>
```

### Temporarily remove uncommitted changes
```bash
$ git stash
```

### Specifies the remote repository for your local repository. The url points to a remote repository
```bash
$ git remote add origin [https://github.com/...]
```

### See remote URLs
```bash
$ git remote -v
```

### Check remote branches that Git is tracking
```bash
$ git branch -r
```

### Fetch remote repo changes
```bash
# download the changes from a remote repo but will not perform a merge
# on your local branch (as git pull does that instead)
$ git fetch
```

## External Links

- [Git Documentation](https://git-scm.com/doc)
- [The Official GitHub, Trainig Manual](https://githubtraining.github.io/training-manual/book.pdf)
- [Interactive Cheatsheet, Visualization Of Git](http://ndpsoftware.com/git-cheatsheet.html#loc=index;)