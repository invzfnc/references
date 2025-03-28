**Should I use multiprocessing, multithreading, or asyncio?**

https://stackoverflow.com/questions/27435284/multiprocessing-vs-multithreading-vs-asyncio

```python
if io_bound:
    if io_very_slow:
        print("Use Asyncio")
    else:
        print("Use Threads")
else:
    print("Multi Processing")
```
- CPU Bound => Multi Processing
- I/O Bound, Fast I/O, Limited Number of Connections => Multi Threading
- I/O Bound, Slow I/O, Many connections => Asyncio



