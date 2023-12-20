1. Setup pattern using `re.compile`
2. Use pattern to search the string

#### `re.compile` - Setup pattern

```python
re.compile(pattern, flags=0)
```

Example
```python
text = "URL: www.google.com"
pattern = re.compile(r"www\.google\.com")
match = pattern.search(text)
print(match)
```
```
Output
<re.Match object; span=(5, 19), match='www.google.com'>
```

##### Special Characters

###### Meta characters (Need to be escaped)
```
. ^ $ * + ? { } [ ] \ | ( )
```

###### Character classes
```
.       - Any Character Except New Line
\d      - Digit (0-9)
\D      - Not a Digit (0-9)
\w      - Word Character (a-z, A-Z, 0-9, _)
\W      - Not a Word Character (symbols, space, newline)
\s      - Whitespace (space, tab, newline)
\S      - Not Whitespace (space, tab, newline)
```

###### Boundaries
```
\b      - Word Boundary
\B      - Not a Word Boundary
```

```python
text = "Ha HaHa"

pattern = re.compile(r"\bHa")
matches = pattern.finditer(text)
for match in matches:
    print(match)
```
```
# Matches first and second Ha in "Ha HaHa"
<re.Match object; span=(67, 69), match='Ha'>
<re.Match object; span=(70, 72), match='Ha'>
```
```python
pattern = re.compile(r"\BHa")
matches = pattern.finditer(text)
for match in matches:
    print(match)
```
```
# Matches third Ha in "Ha HaHa"
<re.Match object; span=(72, 74), match='Ha'>
```

###### Startswith and Endswith
```
^       - Beginning of a String
$       - End of a String
```
```python
sentence = "Start a sentence and then bring it to an end"

pattern = re.compile(r"^Start")
print(pattern.search(sentence))
# <re.Match object; span=(0, 5), match='Start'>

pattern = re.compile(r"^a")
print(pattern.search(sentence))
# None

pattern = re.compile(r"end$")
print(pattern.search(sentence))
# <re.Match object; span=(41, 44), match='end'>

# Does not match if "end" is before a new line / not the end of string)
```

###### Defining custom character sets
```
[]      - Matches Characters in brackets
[^ ]    - Matches Characters NOT in brackets
[a-b]   - Range (a to b)
```
```python
numbers = """
321-555-4321
123.555.1234
123*555*1234
800-555-1234
900-555-1234
"""

# Match one single character that is either -, . or *
pattern = re.compile(r"\d\d\d[-.*]\d\d\d[-.*]\d\d\d\d")
matches = pattern.finditer(numbers)
for match in matches:
    print(match)

# Range
pattern = re.compile(r"[_a-zA-Z0-9]")
# Effect is the same as re.compile(r"\w")
```

###### Quantifiers
```
*       - 0 or More
+       - 1 or More
?       - 0 or One
{3}     - Exact Number
{3,4}   - Range of Numbers (Minimum, Maximum) (Default: match most occurance)
{3,4}?  - Non greedy matching (Match least occurence) 
{3,}    - 3 or more
```

```python
numbers = """
321-555-4321
123.555.1234
123*555*1234
800-555-1234
900-555-1234
"""

pattern = re.compile(r"\d{3}.\d{3}.\d{4}")
# The same as re.compile(r"\d\d\d.\d\d\d.\d\d\d\d")

matches = pattern.finditer(numbers)
for match in matches:
    print(match)
```

###### Grouping with `()` and `|`
```
|       - Either Or
( )     - Group
```

```python
names = """
Mr. Schafer
Mr Smith
Ms Davis
Mrs. Robinson
Mr. T
"""
pattern = re.compile(r"M(r|s|rs)\.?\s[A-Z]\w*")
matches = pattern.finditer(names)
for match in matches:
    print(match)
```
```
Output
# <re.Match object; span=(221, 232), match='Mr. Schafer'>
# <re.Match object; span=(233, 241), match='Mr Smith'>
# <re.Match object; span=(242, 250), match='Ms Davis'>
# <re.Match object; span=(251, 264), match='Mrs. Robinson'>
# <re.Match object; span=(265, 270), match='Mr. T'>
```

<br/>

##### Examples
###### Case: email Matching
```python
emails = """
CoreyMSchafer@gmail.com
corey.schafer@univesity.edu
corey-321-schafer@my-work.net
"""

pattern = re.compile(r"[a-zA-Z0-9.-]+@[a-zA-Z-]+\.(com|edu|net)")
matches = pattern.finditer(emails)
for match in matches:
    print(match)
```

###### Case: URL Matching
```python
urls = """
https://www.google.com
http://coreyms.com
https://youtube.com
https://www.nasa.gov
"""

pattern = re.compile(r"https?://(www\.)?(\w+)(\.\w+)")
matches = pattern.finditer(urls)
for match in matches:
    print(match)

# <re.Match object; span=(1, 23), match='https://www.google.com'>
#<re.Match object; span=(24, 42), match='http://coreyms.com'>
#<re.Match object; span=(43, 62), match='https://youtube.com'>
#<re.Match object; span=(63, 83), match='https://www.nasa.gov'>
```

<br/>

#### `re.Pattern` search methods

|Method|Output|Scope|
|---|---|---|
|`re.search`|1 `re.Match`|Whole string|
|`re.findall`|List of strings or tuples|Whole string|
|`re.finditer`|1 iterator|Whole string|
|`re.match`|1 `re.Match`|Beginning of string|

**`findall`**
```
findall return list of strings or tuples (for grouped pattern)
tuple contains grouped results only, text outside groups will not be returned
```

<br/>

#### `re.Match` methods
##### `group`
```python
pattern = re.compile(r"https?://(www\.)?(\w+)(\.\w+)")
matches = pattern.finditer(urls)
for match in matches:
    print(match.group(0), match.group(1), match.group(2), match.group(3), sep="|")

# https://www.google.com|www.|google|.com
# http://coreyms.com|None|coreyms|.com
# https://youtube.com|None|youtube|.com
# https://www.nasa.gov|www.|nasa|.gov
```

##### `sub`
```python
pattern = re.compile(r"f\w{2}k(ing?)?")

list(pattern.finditer("fvck fvcking fvckin"))
# [<re.Match object; span=(0, 4), match='fvck'>, <re.Match object; span=(5, 12), match='fvcking'>, <re.Match object; span=(13, 19), match='fvckin'>]

pattern.sub("beep", "what the fvcking fvck")
# 'what the beep beep'
```

<br/>

#### Flags
##### `re.A`, `re.ASCII`
Character sets no longer match Unicode characters
eg `Wiktor` is matched with ``\w+``, but `Виктор` does not
`re.UNICODE` is redundant in Python3 since matches are Unicode by default

##### `re.I`, `re.IGNORECASE`
Perform case-insensitive matching
`[A-Z]` will also match `[a-z]`

##### `re.M`, `re.MULTILINE`
Default: `^` matches only at the beginning of the string; `$` only at the end of the string and immediately before the newline (if any) at the end of the string.

Specified: The pattern character `^` matches at the beginning of the string and at the beginning of each line (immediately following each newline); `$` matches at the end of the string and at the end of each line (immediately preceding each newline)

##### `re.S`, `re.DOTALL`
Default: `.` matches any character except newline
Applied: `.` matches any character including newline

##### `re.X`, `re.VERBOSE`
Pattern string supports multiline string (whitespace within pattern is ignored, except for when in a character class, or when preceded by an unescaped backslash), and allows for adding comments

##### `re.NOFLAG`
value=0, default value for `flags` parameter

To specify more than one flag, use pipe
`flags=re.I|re.M|re.X`

<br/>

#### Cheat Sheet
```
MetaCharacters (Need to be escaped):
. ^ $ * + ? { } [ ] \ | ( )

.       - Any Character Except New Line
\d      - Digit (0-9)
\D      - Not a Digit (0-9)
\w      - Word Character (a-z, A-Z, 0-9, _)
\W      - Not a Word Character (symbols, space, newline)
\s      - Whitespace (space, tab, newline)
\S      - Not Whitespace (space, tab, newline)

\b      - Word Boundary
\B      - Not a Word Boundary

^       - Beginning of a String
$       - End of a String

[]      - Matches Characters in brackets
[^ ]    - Matches Characters NOT in brackets
[a-b]   - Range (a to b)

Grouping with Parenthesis and Pipe
|       - Either Or
( )     - Group

Quantifiers
*       - 0 or More
+       - 1 or More
?       - 0 or One
{3}     - Exact Number
{3,4}   - Range of Numbers (Minimum, Maximum)



```


---

[Tutorial](https://youtu.be/K8L6KVGG-7o)