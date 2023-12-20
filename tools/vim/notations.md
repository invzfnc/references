Notations used for Vim notes

#### Sequence

|Notations|Meaning|
|---|---|
|`x`|Press `x` once|
|`dw`|Press `d`, then `w`|
|`dap`|Press `d`, then `a`, then `p`|
|`<C-n>`|Press `Ctrl`+`n` (at the same time)|
|`g<C-]>`|Press `g`, then `Ctrl`+`]` (at the same time)|

#### Placeholders - `{}`

|Notation|Meaning|
|---|---|
|`f{char}`|Press `f`, followed by any other character|
|<code>`{a-z}</code>|Press <code>`</code>, followed by any uppercase character|
|<code>m{a-zA-Z}</code>|Press `m`, followed by any lower or uppercase character|
|`d{motion}`|Press `d`, followed by any motion command|
|`<C-r>{register}`|Press `Ctrl`+`r` (at the same time), followed by the address of a register|

#### Special Keys

|Notation|Meaning|
|---|---|
|`<Esc>`|Escape key|
|`<CR>`|Carriage return key or `<Enter>`|
|`<Ctrl>`|Control key|
|`<Tab>`|Tab key|
|`<Shift>`|Shift key|
|`<S-Tab>`|`<Shift>`+`<Tab>` (at the same time)|
|`<Up>`|Up arrow key|
|`␣`|Space bar|

#### Command Line Interaction

Example: 
`$ grep -n target`  
`:q!`  

|Prompt|Meaning|
|---|---|
|`$`|Enter the command line in an external shell/terminal|
|`:`|Use Command-Line mode to execute an Ex command|
|`/`|Use Command-Line mode to perform a forward search|
|`?`|Use Command-Line mode to perform a backward search|
|`=`|Use Command-Line mode to evaluate a Vim script expression|

`<CR>` is implicit at the end of command  

