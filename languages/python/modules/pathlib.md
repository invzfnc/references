#### `Path` instantiation
``` python
# Passing complete file path
>>> Path("a/b/c")
WindowsPath('a/b/c')

# Passing components
>>> Path("a", "b", "c")
WindowsPath('a/b/c')

# str it
>>> str(_)
'a\\b\\c'

# Slash operator joining paths
>>> Path("a") / "b" / "c"
WindowsPath('a/b/c')
>>> Path("a") / Path("b", "c")
WindowsPath('a/b/c')
```

Additional notes
`Path("folder\\file")` on Windows means file `file` in folder `folder` while on Linux and Mac means the file `folder/file`
`Path` will return `PosixPath` on Linux

#### `Path` static methods
##### `Path.cwd`
```python
>>> Path.cwd()
WindowsPath('C:/Program Files/Python311')
```

##### `Path.home`
```python
>>> Path.home()
WindowsPath('C:/Users/eve')
```
- Windows: `C:\Users`
- Mac: `/Users`
- Linux: `/home`

#### `Path` methods
##### `mkdir`
Creates folder (Limit 1 level, the folder itself)
```python
>>> Path("Z:/newfolder/newfolder").mkdir()
Traceback (most recent call last):
  File "<pyshell#22>", line 1, in <module>
    Path("Z:/newfolder/newfolder").mkdir()
  File "C:\Program Files\Python311\Lib\pathlib.py", line 1116, in mkdir
    os.mkdir(self, mode)
FileNotFoundError: [WinError 3] The system cannot find the path specified: 'Z:\\newfolder\\newfolder'

>>> Path("Z:/newfolder").mkdir()   # Success
```
##### `read_text`
Pass `encoding="utf-8"` just in case
##### `write_text(text)`
Overwrites if file exists, creates new one if does not

##### `is_absolute`
##### `exists`
##### `is_dir`
Returns boolean value

#### `Path` attributes
```python
>>> path = Path("C:", "Users", "eve", "Scripts", "Python", "main.py")
>>> path.anchor  # or drive in windows
'C:'
>>> path.parent
WindowsPath('C:Users/eve/Scripts/Python')
>>> path.name
'main.py'
>>> path.stem  # or basename
'main'
>>> path.suffix  # or suffix or extension
'.py'
```
These attributes evaluate to simple string except for `parent` which evaluates to `Path` object.

```python
>>> path.parent
WindowsPath('C:Users/eve/Scripts/Python')

>>> path.parents
<WindowsPath.parents>

>>> for n, parent in enumerate(path.parents):
    print(f"{n}: {parent}")
    
0: C:Users\eve\Scripts\Python
1: C:Users\eve\Scripts
2: C:Users\eve
3: C:Users
4: C:
```