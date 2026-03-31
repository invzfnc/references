**instructions**: a statement that becomes executable when a program is assembled. instruction consist of parts: `[label:] mnemonic [operands] [;comment]`

#### label
two types of labels: data labels and code labels  
a label placed just before an instruction implies the instruction's address.  
a label placed just before a variable implies the variable's address.  

data label:

```asm
count DWORD 100  ; defines a variable named count

array DWORD 1024, 2048
	  DWORD 4096, 8192
```

code label (must end with colon character):
```asm
; this create a loop
target:
	mov ax,bx
	...
	jmp target

; label can be on the same line as instructions, or on a line by itself
L1: mov ax,bx
L2:
	...
```

