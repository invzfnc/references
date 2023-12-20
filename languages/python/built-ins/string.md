#### Methods

##### `partition`
Always return tuple with 3 values
```python
s = "Lorem ipsum dolor sit amet"

s.partition("dolor")
>>> ('Lorem ipsum ', 'dolor', ' sit amet')

# Separator not found
s.partition("elit")
>>> ('Lorem ipsum dolor sit amet', '', '')

# Multiple assignment
before, sep, after = s.partition("dolor")
before
>>> 'Lorem ipsum '
sep
>>> 'dolor'
after
>>> ' sit amet'
```

##### `strip`
```python
s = "SpamSpamBaconSpamEggsSpamSpam"
s.strip("ampS")
>>> 'BaconSpamEggs'
```


#### Functions

##### `ord`
Return Unicode code point
```python
ord("A")
>>> 65
```

##### `chr`
Return Unicode string
```python
chr(65)
>>> 'A'
```