## Cache memory
Chapter 4, Cache Memory from *Computer Organization and Architecture*

### Characteristics of memory

- **Location**: Internal (main memory, cache, registers) or external (peripheral storage devices such as disks, tape). Separated by one condition: need I/O controller as bridge?
- **Capacity**: Typically expressed in words or bytes for internal memory. Where 1 byte equal 8 bits, and word represents the width of the CPU registers and datapath. In a 64-bit processor, a word is 8 bytes, while 4 bytes in 32-bit processor.
- **Addressable units**:
	- Word:  the "natural" unit of organization of memory.
	- Addressable unit: 2 to the power of length in bits of an address. ($2^A=N$, where $N$ is the addressable units)
- **Unit of transfer**: For main memory, this is the number of bits read out or written into memory at a time. For external memory, this is a block.
- **Method of accessing**: Sequential access, direct access, random access, associative.
- **Performance**
	- Access time (latency): For RAM, latency is the time to read or write. For non RAM, latency is the time it takes to position the read-write mechanism at the desired location.
	- Memory cycle time: Primarily applied to RAM. Consist of access time plus the additional time required before the next access can commence. This is concerned with the system bus, not the processor.
	- Transfer rate: For RAM, this is the inverse of cycle time. For non RAM, this is
		$$ T_n = T_A + \frac{n}{R} $$
		Average time to read or write n bits = Average access time + Number of bits / Transfer rate, or equivalently, average access time + number of bits times memory cycle time.
- **Physical type**
	- Semiconductor
	 - Magnetic
	 - Optical
	 - Magneto-optical
- **Physical characteristics**
	- Volatile/nonvolatile: Magnetic surfaces are non-volatile. Semiconductor memory may be either both.
	 - Erasable/nonerasable: Nonerasable semiconductor memory are also called ROM. This type of memory must also be nonvolatile to be practical.
- **Organization** - Physical arrangement of bits to form words.

### The memory hierarchy

#### Design constraints
- How much: Somehow open ended, applications will be developed to use up the capacity available.
- How fast: Memory must be able to keep up with the processor
- How expensive: Cost of memory must be reasonable in relationship to other components.

#### Tradeoff relationships/dilemma
- Faster access time, greater cost per bit;
- Greater capacity, smaller cost per bit;
- Greater capacity, slower access time.

#### The hierarchy
```
Inboard memory
	Registers
	Cache
	Main memory
Outboard storage
	Magnetic disk
	CD-ROM
	CD-RW
	DVD-RW
	DVD-RAM
	Blu-Ray
Off-line storage
	Magnetic tape
```

As one goes down the hierarchy, the following occur
- Decreasing cost per bit
- Increasing capacity
- Increasing access time
- Decreasing frequency of access by the processor

### Locality

The basis validity of "decreasing frequency of access by the processor" is known as the **locality of reference**. During the execution of program, the instructions and data accessed by the processor tend to cluster. Over a long period of time, the clusters in use tend to change, but over a short period of time, the processor is primarily working with fixed clusters of memory references.

### Cache memory principles

Cache:
- consists of **lines**; main memory consists of **blocks**
- each cache line corresponds to one memory block
- cache line stores:
    - data (same as block)
    - tag (part of memory address)
    - control bits

Control bits:
- **valid bit**: indicates if line contains valid data
- **dirty bit**: indicates if data has been modified in cache (used in write-back)

Operation:
- CPU checks cache first
    - **hit** → return data
    - **miss** → fetch block from memory into cache line
- on miss:
    - load block into line
    - set tag
    - set valid bit

Write-back behavior:
- if data is modified → dirty bit = 1
- when line is replaced:
    - if dirty = 1 → write back to memory
    - if dirty = 0 → no write needed

### Elements of cache design

Virtual memory: Facility that allows programs to address memory from a logical point of view, without regard to the amount of main memory physically available.

When virtual memory is used, the address fields in instructions contains virtual addresses. A hardware **memory management unit** (MMU) translates virtual address into physical address in main memory for reads to and writes from the main memory.

With the involvement of MMU, system designer choose to put cache between the processor and MMU (logical cache/virtual cache), or between the MMU and main memory (physical cache). 

**Physical cache** 
- Stores data using main memory physical addresses. 
- Good: Access speed is faster because the cache can respond before MMU performs address translation. 
- The catch is that multiple programs may share the same virtual addresses. The cache memory must be flushed with each application context switch, or add something unique to identify which virtual address space this address refers to.

**Logical cache**
- Stores data using virtual addresses. 
- Good: The processor accesses the cache directly without going through MMU. 

Modern processors often use a combination: a fast virtually indexed, physically tagged L1 cache (blending both) and physically indexed, physically tagged L2/L3 caches.

### Mapping function

There are fewer cache lines than main memory blocks, an algorithm is needed to decide which blocks map into which lines

#### Direct mapping

$$i = j \bmod m$$

$i =$ cache line number  
$j =$ main memory block number  
$m =$ number of lines in the cache  

Each main memory address consist of three fields.  
Let's say the memory is byte-addressable, so each address refers to 1 byte, and offset selects a byte. If the block size is 4 words, or 4 bytes, the size of offset (w bits) will be $2^2$ bits ($w = 2^2$)

Number of blocks in memory = $2^s$  
Number of cache lines =$2^r$  

More on the [flow](./direct-addressing.md).

Disadvantage: there is a fixed cache location for any given block. Thus, if a program happens to reference words repeatedly from two different blocks that map into the same line, then the blocks will be continually swapped in the cache, and the hit ratio will be low (a phenomenon known as thrashing).

#### Associative mapping

TODO

#### Set-associative mapping

TODO
