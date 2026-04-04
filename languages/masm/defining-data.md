### Data types

Data definition sets aside storage in memory for a variable, with an optional name

```asm
; [name] directive initializer [,initializer]...

count DWORD 12345

; 8-bit integers
c BYTE 'A'
min_ubyte BYTE 0  ; character literal
max_ubyte BYTE 255
min_sbyte SBYTE -128
max_sbyte SBYTE +127
x BYTE ?  ; leave uninitilized, implying it will be assigned at runtime

; 16-bit integers
max_word WORD 65535
max_sword SWORD -32768
w WORD ?  ; uninitialized, unsigned

; 32-bit integers
min_sdword SDWORD -2147483648
max_sdword SDWORD 2147483647

; 64-bit integers
quadword QUAD 1234567812345678h
```

**Intrinsic data types**

|Type|Usage|
|---|---|
|BYTE|8-bit unsigned integer. B stands for byte|
|SBYTE|8-bit signed integer. S stands for signed|
|WORD|16-bit unsigned integer|
|SWORD|16-bit signed integer|
|DWORD|32-bit unsigned integer. D stands for double|
|SDWORD|32-bit signed integer. SD stands for signed double|
|FWORD|48-bit integer (Far pointer in protected mode)|
|QWORD|64-bit integer. Q stands for quad|
|TBYTE|80-bit (10-byte) integer. T stands for Ten-byte|
|REAL4|32-bit (4-byte) IEEE short real|
|REAL8|64-bit (8-byte) IEEE long real|
|REAL10|80-bit (10-byte) IEEE extended real|


**Legacy data directives**

|Type|Usage|
|---|---|
|DB|8-bit integer|
|DW|16-bit integer|
|DD|32-bit integer or real|
|DQ|64-bit integer or real|
|DT|define 80-bit (10-byte) integer|


### Multiple initializers

Its label refers only to the offset of the first initializer

```asm
list BYTE 10,20,30,40 ; a sequence of bytes, each with its own offset
```
Assuming `list` is located at offset `0000`. If so, the value `10` is at offset `0000`, `20` is at offset `0001`, `30` is at `0002`, and `40` is at `0003`.

Not all data definitions require labels. To continue the array of bytes begun with a `list`, for example, we can define additional bytes on the next lines.
```asm
	list BYTE 10,20,30,40
		 BYTE 50,60,70,80
		 BYTE 81,82,83,84
```

### Defining Strings
```asm
greeting1 BYTE "Good afternoon",0
greeting2 BYTE "Good night",0
```

Each character uses a byte of storage, the most common type of strings (null-terminated string) ends with a null byte (containing 0).

Strings are an exception to the rule that byte values must be separated by commas. Or else, `greeting1` would have been:

```asm
greeting1 BYTE 'G','o','o','d',...etc.
```

**Multiline strings**
```asm
greeting1 BYTE "Hello, world!",0dh,0ah
		  BYTE "In case I don't see you,",0dh,0ah
		  BYTE "Good afternoon, "
		  BYTE "good evening, "
		  BYTE "and good night."0dh,0ah,0
```

The hexadecimal codes `0dh`, `0ah` are called CR/LF (carriage return/line feed) or end-of-line characters

**Line continuation**
```asm
; concatenates two source code lines into a single statement.
greeting1 \
BYTE "Hello, world!",0
```

### `DUP` operator

Allocates storage for multiple data items, using an integer expression as a counter. Can be used with initialized or uninitialized data.

```asm
BYTE 20 DUP(0)        ; 20 bytes, all equal to zero
BYTE 20 DUP(?)        ; 20 bytes, uninitialized
BYTE  4 DUP("STACK")  ; 20 bytes: "STACKSTACKSTACKSTACK"

array WORD 5 DUP(?)   ; 5 16-bit values, uninitialized
```

