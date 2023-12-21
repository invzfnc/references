Sync with remote repo

**Getting**
`git clone <repo-url>`
`git clone <repo-url> <dest>`
Clone a remote repo into working directory

`git fetch`
`git fetch <remote-shortname>`
Get all data from remote repo that the local doesn't have yet, does not merge

`git pull`
`git fetch` with `git merge`

**Config**
`git remote`
`git remote -v`
Get detail of tracked remote repositories
`origin` - Default name Git gives to the server cloned from

`git remote add <shortname> <repo-url>`
Add new remote repository
`git remote show <shortname>`
Show information about a particular remote
`git remote rename <from-name> <to-name>`
Rename a remote's shortname
`git remote remove <shortname>`
Remove a remote

**Pushing**
`git push origin <tag>` (push specific tag)
`git push origin --tags` (push all tags)
`git push origin --follow-tags` (push only annotated tags)
`git push` by default does not push tags to remote servers, therefore have to explicitly push them

