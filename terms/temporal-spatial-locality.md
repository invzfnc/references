**Temporal locality** - recently used, likely reused. If you accessed something now, you'll probably access it again soon.

```c
// example
for (int i = 0; i < 1000; i++) {
	sum += x;
}
```
- the variable `x` is used over and over
- the cpu keeps `x`in registers or cache

what if `sum += i`? `i` is a loop variable, it is usually stored in the register, not memory, so it doesn't even need cache most of the time, the cpu updates it directly in registers.

**Spatial locality** - nearby, likely used soon. If you accessed something, you'll likely access nearby data soon.

```c
// example
for (int i = 0; i < 1000; i++) {
	sum += arr[i];
}
```
- the system loads a chunk (cache line), not just one element

temporal locality: reuse recent data  
spatial locality: preload nearby data