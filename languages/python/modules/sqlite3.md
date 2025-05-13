```python
import sqlite3
```

```python
connection = sqlite3.connect(filename, isolation_level=None)
```
Opens a connection to the SQLite database file database
- `filename`: String or `pathlib.Path` object. Creates new file with empty database if does not exist.
- `isolation_level`: "The `isolation_level=None` keyword argument causes the database to use write-ahead logging, or WAL mode. In general, “always use WAL mode” is good advice for beginners."
- Returns a `Connection` object.

```python
connection.close()
```
Closes connection.

```python
connection.execute(query)
```
`query`: string

```python
sqlite3.sqlite_version
> '3.42.0'
```
Check SQLite version.

#### SQLite Data Types

- `NULL` - `None`
- `INT`/`INTEGER` - Integer
- `REAL` - Float
- `TEXT` - String
- `BLOB` -  Binary Large Object, `bytes`
- `ANY` - Any

#### CRUD Database Operations
Stands for: Create, Read, Update, Delete
SQLite equivalent operations: INSERT, SELECT, UPDATE, DELETE
