or *Anonymous function*

```python
addition = lambda x, y: x + y
addition(1, 3) # == 4
```

With conditions
```python
# Lambda
lambda answer: 1 if answer.lower() == "yes" else 0

# Function
def func(answer):
    if answer.lower() == "yes":
        return 1
    else:
        return 0
```