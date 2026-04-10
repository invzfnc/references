### `.data?` directive

This code:
```asm
.data
smallArray DWORD 10 DUP(0) ; 40 bytes
.data?
bigArray DWORD 5000 DUP(?) ; 20,000 bytes, not initialized
```

is 20000 bytes lesser than this code:
```asm
.data
smallArray DWORD 10 DUP(0) ; 40 bytes
bigArray DWORD 5000 DUP(?) ; 20,000 bytes
```

The `.DATA?` directive declares uninitialized data. When defining a large block of uninitialized data, this directive reduces the size of the compiled program.

### Mixing code and data

```asm
.code
mov eax,ebx
.data
temp DWORD ?
.code
mov temp,eax
```

`temp` is declared to be used within a local-sized area of program. MASM places the `temp` in the data segment, separate from the segment holding the compiled code.

However, this can make the code hard to read.