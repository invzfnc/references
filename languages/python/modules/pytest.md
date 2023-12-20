A *unit test* verifies that one specific aspect of the function's behavior is correct. A *test case* is a collection of unit tests that together prove that a function behaves as it's supposed to, within the full range of situations you expect it to handle.

```python
# test_function_x.py

def test_function_x():
    """Do inputs like 'x' work?"""
    output = function_x("x")
    assert output == "desired output"
```

- Name of the test file must start with `test_`, like `test_function_x.py`
- Name of the test function must start with `test_`, like `test_function_x`
- Test names should be longer and descriptive than usual, you'll never call the function yourself and you'll need a good sense of what behavior was being tested.
- Make assertions (`output == desired output`)

#### Type of assertions

```python
assert a == b
assert a != b
assert a  # Evaluates to True
assert not a  # Evaluates to False
assert element in list
assert element not in list
```

#### Fixture (Setup)

```python
import pytest

@pytest.fixture
def variable_x():
    ... # Define variable_x
    return variable_x

# Test function
def test_variable_x(variable_x):
    assert variable_x == "some value"
```

1. Decorator `@pytest.fixture`
2. Define function with the name of variable to be setup
3. Make the function return the value of the variable
4. Set parameter to the name of fixture function in the test function

When a parameter matches the name of a function with the `@pytest.fixture` decorator, the fixture will be run automatically and the return value will be passed to the text function