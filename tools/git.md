#### Basic/Common Workflow

`git init`
Initialize repository

`git clone <url>`
`git clone <url> <directory>`
Clone from an online repository

`git add <filename>` 
`git add .` (all)
Stage modified files

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

`git log`
`git log -p` (patch/show diff)
`git log -2` (two recent entries)
`git log --stat` (abbreviated stats for each commit)
View commit history

`git diff`
`git diff --staged`
View change details

#### Config Setup

```
git config user.name <name>
git config user.email <email>
git config --global init.defaultBranch main
git config --global core.editor vim
```

`git config --list`
View all settings

`git config --list --show-origin`
View all settings and where they are coming from

`git config <keyword>`
Check the value of `keykword`, eg `user.name`

`git config --global alias.co checkout`
`git config --global alias.last 'log -1 HEAD'`

#### `.gitignore`
```gitignore
# ignore all .a and .o files
*.[oa]

# but do track lib.a, even though you're ignoring .a files above
!lib.a

# ignore files ending with ~
*~

# only ignore the TODO file in the current directory, not subdir/TODO
/TODO

# ignore all files in any directory named build
build/

# ignore doc/notes.txt, but not doc/server/arch.txt
doc/*.txt

# ignore all .pdf files in the doc/ directory and any of its subdirectories
doc/**/*.pdf
```
- Start patterns with `/` to avoid recursivity 
- Glob patterns are like simplified regular expressions that shells use

```
*       - Zero or more
?       - One or more
[abc]   - Either
[0-9]   - Range
a/**/z  - Match nested directories, eg a/z, a/b/z, a/b/c/z
```

#### Basic Remote Operations
`git clone <repo-url>`
`git clone <repo-url> <dest>`
Clone a remote repo into working directory

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

`git fetch`
`git fetch <remote-shortname>`
Get all data from remote repo that the local doesn't have yet, does not merge

`git pull`
`git fetch` with `git merge`


#### Tags

**Checking**
`git tag`
List existing tags in repo
`git tag --list "v1.8.*"`
With wildcard pattern

**Adding**
`git tag -a <tag>`
`git tag -a <tag> -m <message>`
Create an annotated tag
`git tag <tag>`
Create a lightweight tag
`git tag -a <tag> <commit-checksum>`
Put tag to a specific commit

**Deleting**
`git tag -d <tag>`
Effect: Put into detached HEAD state. Commits in this state does not apply anywhere, need to create branch with `git checkout -b <branch-name> <tag>)

**Pushing**
`git push origin <tag>` (push specific tag)
`git push origin --tags` (push all tags)
`git push origin --follow-tags` (push only annotated tags)
`git push` by default does not push tags to remote servers, therefore have to explicitly push them

