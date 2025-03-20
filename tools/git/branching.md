`git checkout -b branchname`
Create a new branch then switch to it
Equivalent:
`git branch branchname`
`git checkout branchname`

`git checkout main`
Switch to `main` branch

`git checkout main`
`git merge hotfix`
Merge `hotfix` into `main`

`git branch -d hotfix`
Delete `hotfix` branch

`git branch`
List all branches

`git branch --move bad-branch-name corrected-branch-name`
Rename branch

`git push --set-upstream origin corrected-branch-name`
`git push origin --delete bad-branch-name`
Push change (the renaming) to remote

`git branch --move master main`
`git push --set-upstream origin main`
`git push origin --delete master`
Rename `master` branch to `main`

`git remote show <remote>`
`git remote show origin`
List remote references explicitly
