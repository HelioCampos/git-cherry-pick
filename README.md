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
Create a new branch, change branches and write 1 commit to it with the message "AA"
```
git checkout -b my_new_branch
echo "[001] - AA - This is the fisrt modification made in the branch called [my_new_branch]" >> hello-git-cherry-pick.txt
git add hello-git-cherry-pick.txt
git add README.md
git commit -m "AA"
```
Change back to the master branch and commit these changes:
```
git checkout master
echo "[002] - Hello master branch updated before cherry-pick!" >> hello-git-cherry-pick.txt
git add hello-git-cherry-pick.txt
git add README.md
git commit -m "A"
```
## Cherry pick
Checkout to the branch "my_new_branch" and get the ID of the commit to be cherry-picked:
```
git checkout my_new_branch
cherry_pick_id=$(git log --oneline | grep AA | cut -d" " -f 1)
```
Checkout to maste rbanch again and make the cherry-pick:
```
git checkout master
git cherry-pick $cherry_pick_id
```
This will apply the same changed but apply a new commit
