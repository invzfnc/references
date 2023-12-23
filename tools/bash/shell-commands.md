Prompt
`$` - User
`#` - root

`sudo su` - Open root terminal

`~` - `/home/<user>`
`-` - Previous working directory

`xdg-open .` - Open file explorer
`xdg-open file` - Launch default app to open file

`echo -n`
echo without newline

`cd` (Without arguments)
To `/home/<user>`

`rm filename`
`rm -r foldername`
Permanently delete file/folder

`rmdir dirname`
Removes empty directory

`cp src dest`
Copy files

`mv old new`
Move/Rename file

`which filename`
Print absolute path of `filename` in `$PATH`

`ls -l`
Long listing format - detailed list of files in directory, along with file permissions
`ls -l -h` - Human readable
`ls -a` - Do not ignore entries starting with `.`

`man program`
Manual

`cat file`
Prints content of the file
`cat < hello.txt > hello2.txt` == `cp hello.txt hello2.txt`

`Ctrl-L`
Clear screen

`Ctrl-D`
EOF

`tail --lines x [filename]`
`tail -nx [filename]`
Outputs last `x` lines of input stream
`ls -l | tail -n1 > last_line.txt` - Write last line of output of `ls -l` to `last_line.txt`
`echo line > hello.txt` - Write `line` into `hello.txt`

Stream redirections
`x > y` - x input to y
`x < y` - y input to x 
`x >> y` - x append to y
`x | y` - Take the output of x and give it to y / input it to y

`cat <(ls) <(ls ..)`
Prints result of `ls` followed by `ls ..`

`tee`
`echo hello | tee file`
Redirects output stream of left side to right side, `tee` then writes input to both `stdout` and to `file`

`/dev/null`
`grep foobar filename > /dev/null 2> /dev/null`
Throw away/suppress output