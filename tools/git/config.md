Configuration setup

```
git config --global user.name <name>
git config --global user.email <email>
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

Changing config to local repo (exclusion, ~global)
```
git config user.name anotherUser
git config user.email anotherUserEmail
git config credential.username anotherUser
```
