**Shortcut Keys**

|Key|Effect|
|---|---|
|`<C-]>`|Indent|
|`<C-[>`|Unindent|
|`<C-/>`|Comment or Uncomment|
|`<Alt-Up>` `<Alt-Down>`|Move block or line up or down|
|`<C-b>`|Toggle explorer pane|

**Configuration file**

 Debugging - `launch.json`
 ```json
 "stopOnEntry": true,
 "justMyCode": false

 ```
 
 Ignore import error in Pylint
 ```python
 # pylint: disable=no-member
 ```
