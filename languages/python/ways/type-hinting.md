"Python will remain a dynamically typed language, and the authors have no desire to ever make type hints mandatory, even by convention." [src](https://peps.python.org/pep-0484/#non-goals)

Snippet from https://mypy.readthedocs.io/en/stable/cheat_sheet_py3.html

```python
# For most types, just use the name of the type in the annotation
# Note that mypy can usually infer the type of a variable from its value,
# so technically these annotations are redundant
x: int = 1
x: float = 1.0
x: bool = True
x: str = "test"
x: bytes = b"test"

# For collections on Python 3.9+, the type of the collection item is in brackets
x: list[int] = [1]
x: set[int] = {6, 7}

# For mappings, we need the types of both keys and values
x: dict[str, float] = {"field": 2.0}  # Python 3.9+

# For tuples of fixed size, we specify the types of all the elements
x: tuple[int, str, float] = (3, "yes", 7.5)  # Python 3.9+

# For tuples of variable size, we use one type and ellipsis
x: tuple[int, ...] = (1, 2, 3)  # Python 3.9+

# On Python 3.8 and earlier, the name of the collection type is
# capitalized, and the type is imported from the 'typing' module
from typing import List, Set, Dict, Tuple
x: List[int] = [1]
x: Set[int] = {6, 7}
x: Dict[str, float] = {"field": 2.0}
x: Tuple[int, str, float] = (3, "yes", 7.5)
x: Tuple[int, ...] = (1, 2, 3)

from typing import Union, Optional

# On Python 3.10+, use the | operator when something could be one of a few types
x: list[int | str] = [3, 5, "test", "fun"]  # Python 3.10+
# On earlier versions, use Union
x: list[Union[int, str]] = [3, 5, "test", "fun"]

# Use Optional[X] for a value that could be None
# Optional[X] is the same as X | None or Union[X, None]
x: Optional[str] = "something" if some_condition() else None
if x is not None:
    # Mypy understands x won't be None here because of the if-statement
    print(x.upper())
# If you know a value can never be None due to some logic that mypy doesn't
# understand, use an assert
assert x is not None
print(x.upper())
```

**Variable Annotations**
```python
answer: int = 42
```

**Function Annotations**
```python
def f(x: int, y: int = 5) -> float:
    ...
```