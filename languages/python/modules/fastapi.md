### Quick Start
#### Installation
```sh
python -m pip install "fastapi[standard]"
```

#### First step
```python
# main.py

from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def read_root():
    return {"Hello": "World"}

@app.get("/items/{item_id}")
def read_item(item_id: int, q: str | None = None):
	return {"item_id": item_id, "q": q}

# positional argument : path parameter  : item_id (int)
# optional argument   : query parameter : q (str or None) with default value of None
```

#### Start development server
```sh
fastapi dev main.py
```
Then visit `http://127.0.0.1:8000`, `{"Hello":"World}` should be visible.
When visiting `http://127.0.0.1:8000/items/1?q=somequery`, page shows `{"item_id":1,"q":"somequery"}`.

An API is created, received HTTP requests in the paths and both paths take GET operations. `item_id` is a path parameter, `q` is an optional query  parameter.

#### Automatic interactive API docs
- Swagger UI: `http://127.0.0.1:8000/docs`
- ReDoc: `http://127.0.0.1:8000/redoc`

#### PUT requests
Add this on top
```python
from pydantic import BaseModel

class Item(BaseModel):
	name: str
	price: float
	is_offer: bool | None = None
```

Add this function
```python
@app.put("items/{item_id}")
def update_item(item_id: int, item: Item):
    return {"item_name": item.name, "item_id": item_id}
```

Go to `/docs`, then `Try it out` to test the API directly.

### Path Parameters
```python
# this path parameter `arg` below
@app.get("/patharg/{arg}")
def test_path_argument(arg: str):
    return {"all capitals": arg.upper()}
# will be passed into function test_path_argument as the argument `arg`

# type declaration is possible. will check type strictly
```

