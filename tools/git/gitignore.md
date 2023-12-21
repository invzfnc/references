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

