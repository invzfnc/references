## Direct addressing, flow
1. When CPU wants data, it sends memory address. Example:
	```
	CPU → Cache: Address = 101101... (24 bits)
	```

2. **Cache hardware** splits the address:
	
	```
	[tag | line | word]
	```
	
	* **line (r bits)** → which cache line to look at
	* **tag (s−r bits)** → check if correct block is there
	* **word (w bits)** → which byte inside block

3. Cache lookup - uses **line bits** to pick 1 cache line
4. Check hit or miss by comparing address tag and stored tag. also check valid bit.
	1. If hit (cache already has the block), use **word bits** to select the exact byte, then send **data back to CPU**. Only data is returned, not the address.
	2. If miss (cache doesn't have the block), cache requests from main memory by sending **block address** (not full byte address). Memory sends entire block (e.g., 4 bytes)
		```
		Memory → Cache: [byte0 byte1 byte2 byte3]
		```
		Then, store block in select line, store tag, and set control bit valid=1, dirty=0.
5.  Return requested data. Use **word bits** to pick correct byte and send to CPU.

### Big picture flow

```
CPU → (address) → Cache
        ↓
     [hit?]
     /     \
   yes      no
   ↓        ↓
data ←   Memory request (block)
   ↓        ↓
 CPU     block returned
              ↓
          cache updated
              ↓
           data → CPU
```

### Minimal note version

- CPU sends **address**
- cache splits → **tag | line | word**
- hit:
    - return **data**
- miss:
    - cache sends **block address** to memory
    - memory returns **full block**
    - cache stores block + tag
    - return **requested data**

### About `s - r`

Tag size is (s - r). It comes from whatever bits are left. Only part of the block address is enough, because the full block address = (tag + line). The line bits are already used to select cache line.

In direct addressing, "line" portion is $i$ , where $i = j \bmod m$, and "tag" is $\left\lfloor \frac{j}{m} \right\rfloor$. (`j // m` in Python, or integer division, or floor division)