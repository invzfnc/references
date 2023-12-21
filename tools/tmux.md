`tmux new`
`tmux new -s sessionname`
Create new session

`tmux ls`
List session

`tmux attach`
`tmux attach -t sessionname`
Attach session (Resume running sessions)

**Inside tmux**
`C-b &` Kill session
`C-b $` Rename session
`C-b d` Detach (Exit and let run in background)