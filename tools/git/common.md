Common workflow in git

`git init`
Initialize repository

`git add <filename>` 
`git add .` (all)
Add to staging area / Stage modified files

`git restore --staged <filename>`
Unstage staged file

`git restore <filename>`
Revert changes (modified -> state in commit)

`git rm <filename/pattern>`
Remove tracked file from staging area and working directory/tree or,
remove tracked file from staging area (file is removed from working directory not by git)
`git rm --cached <filename/pattern>`
Remove tracked file from staging area but keep it in the working directory/tree

`git mv <from-file> <to-file>`
Use this over `mv`, effect: `mv` and update index/staging area
```
equivalent to:
mv FROM TO
git rm FROM
git add TO
```

`git commit`
`git commit -m <message>`
`git commit -v`
Commit staged files
`-m` One line commit message
`-v` Verbose: Show diff
`git commit -a`
Commit every tracked but not staged file

`git commit --amend`
Replaces the last commit with a new commit (usually for fixing a typo in commit message or adding the missed file)
Only amend local commits, amending pushed commits and force pushing the branch will cause problems for collaborators

`git status`
Show the working tree status

`git status -s`
Short status
`??` - Untracked
`A` - Added
`M` - Modified
`D` - Deleted

`git log`
View commit history
`git log --patch`, `-p`, patch/show diff
`git log -2`, two recent entries
`git log --stat`, abbreviated stats for each commit
`git log --pretty`, pretty printed output, see [here](./pretty-log.md)

`git diff`
Compare staging area to directory
See what has been changed but not yet staged
`git diff --staged`
Compare staged changes to last commit

`git revert -n HEAD~<n>..HEAD`
Revert working folder to `<n>`th commit state
```gitlog
$ git log --oneline
ba30c26 (HEAD -> master) Revert "Added functionality to eggs function"
38c9dc6 Added functionality to eggs function
c80616a Added bacon function to bacon.py
aa6d571 Added eggs function to eggs.py
0748101 Created bacon.py and eggs.py
```
In this case, `<n>` would be `1` for `ba30c26`

`git checkout <hash> -- <filename>`
	Restore the `<filename>` in `<hash>`  commit state