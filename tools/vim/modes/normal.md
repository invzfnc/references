`k` - Navigate up  
`j` - Navigate down  
`h` - Navigate left  
`l` - Navigate right  

`C-d` - Navigate up
`C-u` - Navigate down

`i` - Switch to Insert Mode  
`R` - Switch to Replace Mode  
`v` - Switch to Visual Mode  
`V` - Line Visual Mode  
`<C-v>` - Block Visual Mode  
`gv` - Switch to Virtual Replace Mode  
`<Esc>` - Return to Normal Mode (`<C-c>` equivalent, recommended)  

`L` - Move cursor to lowest line (viewable)
`M` - Move cursor to line in middle (viewable)
`H` - Move cursor to highest line (viewable)

`w` - Move cursor to start of next word  
`e` - Move cursor to end of word  
`b` - Move cursor to start of previous word  
`W` - `w` but ignores punctuation  
`E` - `e` but ignores punctuation  
`B` - `b` but ignores punctuation  
`gg` - Position cursor at start of file  
`G` - Position cursor at last line of file  
`zz` - Center page relative to cursor  
`zt` - Position cursor at top of screen  
`zb` - Position cursor at bottom of screen  
`$` - Move cursor to end of line  
`0` - Move cursor to start of line  
`^` - Move cursor to first non-whitespace character in line  

(Common effect: Switch to Insert Mode after action)  
`o` - Open new line under the cursor  
`O` - Open new line above cursor  
`a` - Append after current cursor position  
`A` - Append at end of line / `$a` equivalent  
`C` - Change from current position to end of line / `c$` equivalent  
`s` - Substitute character / `cl` equivalent  
`S` - Substitute line / `cc`, `^C` equivalent  
`I` - Move cursor to start of line / `^i` equivalent  
`gi` - Position cursor to last inserted position  

`.` - Repeat the last change/action  
`u` - undo (`i{insert some text}<Esc>` is a change)  

`x` - Delete current character / `dl` equivalent  
`dd` - Delete current line  
`daw` - Delete current word  
`dap` - Delete current paragraph  

`>>` - Increase indentation of current line  
`>G` - Increase indentation from current line until the end of file  

`J` - Join two lines  

(On current line, with one character)  
`f{char}` - Search/Find for character on current line (and move cursor to search result)  
`t{char}` - `f{char}` with offset of 1 (Right before or right after the target)  
`;` - Move cursor to next instance of search results  
`,` - Move cursor to previous instance of search results  

(Entire file, with search patterns)  
`*` - Search for word under cursor  
`/{a-zA-Z}` - Search for word  
`n` - Move cursor to next instance of search results  
`N` - Move cursor to previous instance of search results  

`<C-a>` - Perform addition on number  
`<C-x>` - Perform subtraction on number  
`10<C-a>` - Prefixed: Add 10 to the number  
If cursor is not already positioned on a number, then the command will look ahead for a digit on the current line  

`ga` - Output numeric code for character under cursor  

**Modifiers**
`i` - Inside. Example: `di[`, delete words within brackets
`a` - Around. Example: `da[`, delete words along with brackets