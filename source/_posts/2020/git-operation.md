---
title: Git Operation
permalink: git-operation
date: 2020-04-26 15:40:43
tags: [git]
categories: []
---
Don't afraid to use Git! even break it!
## Git Operations
### Git Basics
```bash
git branch        check current branch

git stauts        check changes of current branch

git checkout -b 'my-new-feature'            create a new branch and change to it

git commit -am 'Add some feature'

# Set upstream(bind) with remote feature branch
git push --set-upstream origin <remote-branch-name>
```

### Git Reset
```bash 
git reset <commit-hash>
# specific file
git reset <commit-hash> -- <file1> <file2>

# will lose changes
git reset --hard HEAD~1
# keep changes
git reset --soft 5029f0cc08cf
```

### Git Diff
```bash 
git apply changes.diff
```

