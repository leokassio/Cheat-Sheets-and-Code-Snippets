# Git

## Credentials
Configure the username, but it still require the password.
```shell
~: git config credential.username leokassio
```

## Git workflow
```shell
# pull the current state of master
~: git pull master
# create a new branch
~: git checkout -b new-branch-name

# make the changes...

# add the files to the commit
~: git add filename # or -u to add all changed files
# register the commit
~: git commit -m "commit message"
# push the changes to a push/merge request
~: git push
```

In case of changes in the master after the creation of your branch, 
it's highly recomended to merge the current branch to the master before the push. 
To do it, you just need
```shell
~: git checkout master
~: git pull
~: git checkout branch-name
~: git merge master
```

## Stashing
Stash is a popular method to save your current work that is not ready to be commited when you need to change to another branch.
```shell
# save your current work
~: git stash save "stash message - good to remember you of what is it about"
# do your stuffs in another branch...
# load your work
~: git stash apply
```
