A closure is an inner function that remembers and has access to variables in the local scope in which it was created even after the outer function has finished executing

Or

A function that has an environment of its own and is defined inside another function

```python
def f(x):
    def g(y):
        return x + y
    return g  # Return a closure.

def h(x):
    return lambda y: x + y  # Return a closure.

# Assigning specific closures to variables.
a = f(1)
b = h(1)

# Using the closures stored in variables.
assert a(5) == 6
assert b(5) == 6

# Using closures without binding them to variables first.
assert f(1)(5) == 6  # f(1) is the closure.
assert h(1)(5) == 6  # h(1) is the closure.

# https://en.wikipedia.org/wiki/Closure_(computer_programming)
```

```python
def outer():
	x = 10
	def inner():
		print(x)   # x is local to the scope where the function was defined

```