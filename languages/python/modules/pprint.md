#### `pprint`
Prints prettified presentation of arbitrary data types

Parameters (Commonly used)
- `indent`
- `width`
- `compact`

```python
li = ['spam', 'bacon', 'ham', 'cheese']

# Setting compact to True fits in 
# more than one element on a line
pprint.pprint(li, width=20, compact=True)
>>> ['spam', 'bacon',
     'ham', 'cheese']
     
# Sets width limit to length of list (str)
pprint.pprint(li, width=len(str(li)))
>>> ['spam', 'bacon', 'ham', 'cheese']

# width < length of item, formatting occurs
pprint.pprint(li, width=20)
>>> ['spam',
     'bacon',
     'ham',
     'cheese']
```

#### `pformat`
Does not print results, instead returns a string containing the results

#### `PrettyPrinter` class
Parameters are the same as `pprint` function
`pp = PrettyPrinter(arguments)` then `pp.pprint(item)` 
instead of 
`pprint(item, arguments)`

Useful for multiple `pprint` calls with the same configuration (since arguments can get tedious sometimes)