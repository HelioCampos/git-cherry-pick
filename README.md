# Git Cherry Pick

This tutorial explains how to use a git-cherry-pick to bring specifics commits from one branch to another.

## Initial configuration
Create a new repository locally
```
mkdir git-cherry-pick
cd !$
git init
```
Write some content to the repo and commit the changes:
```
echo "[000] - Hello git-cherry-pick!" > hello-git-cherry-pick.txt
git add hello-git-cherry-pick.txt
git commit -m "Initial commit"
```


