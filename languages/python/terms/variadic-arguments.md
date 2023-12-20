**Variadic function**
Function that accepts a variable number of arguments

*Variadic arguments* = *Arbitrary arguments lists*
Packs multiple arguments into a single *variadic parameter* or *variadic positional parameter*

```python
def f(*x):
    for arg in x:
        print(arg)
# Variadic function: f
# Variadic parameter: x
```