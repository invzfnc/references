Stream: Sequence of data / flow of data
Types of streams with respect to buffering

1. Unbuffered
	No buffering is taking place, all writes have immediate effect. 
	Example: Countdown is printed one by one
2. Line-buffered
	Waits before firing any I/O calls until a line break appears somewhere in the buffer
3. Block-buffered
	Allows the buffer to fill up a certain size regardless of its contents (such as newlines)

`stdout` is both line-buffered and block-buffered, and which is the reason the program stays idle for `n` seconds before suddenly printing out the entire line at once.
Buffering helps to reduce the number of expensive I/O calls. By postponing the writes, and writing a large block in one go, performance is improved.

https://realpython.com/python-print/#buffering-print-calls
https://stackoverflow.com/questions/15042849/what-does-flushing-the-buffer-mean