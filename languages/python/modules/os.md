#### Variables
- `os.path.sep`, `os.sep` - Path separator
- `os.name` -  `nt`, `posix`, `mac`, `os2`, `ce`, `java`
- `os.linesep` - `\r` or `\n` or `\r\n`
- `os.curdir` - `.`
- `os.pardir` - `..`

#### Functions

##### `getcwd`
Get current working directory

##### `chdir`
Change current working directory

##### `listdir`
Return list containing names of file and directory in cwd

##### `unlink`
##### `remove`
Delete file
`unlink` has the same effect as `remove`

##### `rmdir`
Delete folder

##### `mkdir`
Create a single directory

##### `makedirs`
Recursive `mkdir`

##### `walk`
Return a generator of `(current_folder_name, subfolders_list, subfiles_list)` combinations

##### `system`
Execute the command in a subshell

#### `os.path`

##### `os.path.isabs`
Return True if a path is absolute

##### `os.path.getsize`
Return size of file or folder in bytes

##### `os.path.abspath`
Return the absolute path of a path

##### `os.path.relpath(path, start=None)`
Return the relative path of a path

```python
os.path.relpath(r"C:\Users")
>>> '..\\..\\..\\..\\..\\..'
```

##### `os.path.split`
Return tuple (head, tail) where tail is everything after the final slash
```python
os.path.split(os.getcwd())
>>> ('C:\\Users\\eve\\AppData\\Local\\Programs\\Python', 'Python39')
```

##### `os.path.exists`
Return True if a path exists

##### `os.path.getatime`
Return the last access time of a file
```python
os.path.getatime("python.exe")
>>> 1693551853.4009326

time.localtime(_)
>>> time.struct_time(tm_year=2023, tm_mon=9, tm_mday=1, tm_hour=15, tm_min=4, tm_sec=13, tm_wday=4, tm_yday=244, tm_isdst=0)

time.strftime("%Y/%m/%d %H:%M:%S", _)
>>> '2023/09/01 15:04:13'
```

##### `os.path.getmtime`
Return the last modification time of a file

##### `os.path.getctime`
Return the metadata change time of a file / Time created

