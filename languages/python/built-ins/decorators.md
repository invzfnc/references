```python
import functools

def decorator(func):
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        # Modification to func goes here
        # Calling func
        result = func(*args, **kwargs)
        # Return result of func
        return result
    return wrapper

# Using the decorator
@decorator
def func(x):
    ...
```

`functools.wraps(func)`
Prevents the callable being wrapped from having its identity concealed from the rest of the program. Without this line, wrapping the callable would mess up external access of such important function attributes as `__doc__` (docstring) and `__name__`.  This line itself is a decorator that ensures all the important attributes of the callable are retained by the now-wrapped function, thus making them accessible outside the function in all the usual ways.

Without the line `functools.wraps(func)` the program still runs fine, however the function being wrapped will lose its attributes, as below
```python
__name__ == "wrapper"
__doc__ == None
```