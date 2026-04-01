```asm
; AddTwo.asm - adds two 32-bit integers.
; Chapter 3 example

.386  ; identifies as a 32-bit program that can acccess 32-bit registers and addresses

.model flat,stdcall  ; .model directive tells the assembler which memory model to use,
					 ; in 32-bit programs, we always use the flat memory model
					 ; stdcall tells the assembler how to manage the runtime stack

.stack 4096          ; set aside 4096 bytes of storage for runtime stack

ExitProcess PROTO,dwExitCode:DWORD  ; dwExitCode is the input parameter for ExitProcess

; .data and .code are segments
.data             ; this is the data area
sum DWORD 0       ; create a variable named sum (32 bits)

.code     ; this is the code area
main PROC         ; program entry point. usually a procedure named main
	mov	eax,5     ; move 5 to eax register. default radix is decimal
	add	eax,6   ; add 6 to eax register
	mov sum,eax   ; move eax to sum

 	INVOKE ExitProcess,0  ; end program
main ENDP		  ; endp directive marks the end of the program.
END main		  ; marks the end of the program. references the program entry point: main
; ANY line after the end directive will be ignored by the assembler.
```

```asm
; Program template (Template.asm)

.386
.model flat,stdcall
.stack 4096
ExitProcess PROTO, dwExitCode:DWORD

.data
	; declare variables here
	
.code
main PROC
	; write your code here
	
	INVOKE ExitProcess,0
main ENDP
END main
```