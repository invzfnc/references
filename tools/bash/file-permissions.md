#### Access Modes
`drwxr-xr-x`  
`-rw-r--r--`  
`d111222333`  
`lrwxrwxrwx`  

##### Unix File Type
3 bits to represent 7 file types

`-` - File
`d` - Directory  
`l` - Symbolic link
`p` - Named pipe
`s` - Socket
`b` - Device file (block)
`c` - Device file (character)

##### Permissions / Mode
9 bits / 3
**Group 1**  
`u` - Owner permissions
**Group 2**  
`g` - Group permissions
**Group 3**  
`o` - Other/world permissions

Files
`r` - Open the file and read  
`w` - Append lines, save to file, replace entirely  
`x` - Execute file  

Folders
`r` - List: Are you allowed to see which file is in the directory?  
`w` - Rename, create or delete files within the directory  
`x` - Are you allowed to enter this directory? / `cd` into directory  

Example
`-rwxr-xr--`
Owner has read, write, and execute permission.  
Group can read and execute, but not write to file.  
Other users can only read the file.  

#### `chmod`
`chmod u+w file` - Add execute permission for user
`chmod o-w file` - Remove write permission for others
`chmod ugo=rx file` - Add read and execute permission for everyone
`chmod a=rx file` - All: `a` == `ugo`