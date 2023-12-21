Repo tags

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
