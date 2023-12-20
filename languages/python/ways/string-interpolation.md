
```python
# Single substitution
"Inserts a %s here" %("string")
>>> 'Inserts a string here

# Multiple substitution with mapping key
"Inserts a %(s1)s and a %(s2)s here" %{"s1": "string-one", "s2": "string-two"}
>>> 'Inserts a string-one and a string-two here'

# Rjust with padding (5)
"%5d" %(12)
>>> '   12'

# Ljust with padding (5)
"%-5d" %(12)
>>> '12   '

# With sign character
"%+5d" %(12)
>>> '  +12'
"%-5d" %(-12)
>>> '-12  '
```

`%()s`: Specifier
- Starts with `%` (Mandatory)
- Mapping key, keyword in parenthesis, mostly for multiple assignments
- Conversion flags, `#`, `0`, `-`, ` `, `+`
- Minimum field width
- Precision
- Length modifier
- Conversion type (Mandatory)

[Full Documentation](https://docs.python.org/3/library/stdtypes.html#printf-style-string-formatting)